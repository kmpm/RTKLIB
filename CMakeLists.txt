cmake_minimum_required (VERSION 3.5)
project (rtklib)


# Set the output folder where your program will be created
set(CMAKE_BINARY_DIR ${CMAKE_SOURCE_DIR}/bin)
set(EXECUTABLE_OUTPUT_PATH ${CMAKE_BINARY_DIR})
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR})

set(SRC_DIR ${CMAKE_SOURCE_DIR}/src)


# set(CMAKE_C_FLAGS_DEBUG "put your flags")
# set(CMAKE_C_FLAGS_MINSIZEREL "put your flags")
# set(CMAKE_C_FLAGS_RELWITHDEBINFO "put your flags")
# set(CMAKE_C_FLAGS_RELEASE "put your flags")

# for beagleboard
#CTARGET= -mfpu=neon -mfloat-abi=softfp -ffast-math
# set(CTARGET)

message(STATUS "CMAKE_BUILD_TYPE=${CMAKE_BUILD_TYPE}")
add_definitions("-DENAGLO -DENAGAL -DENAQZS -DENACMP -DENAIRN -DTRACE -DNFREQ=3 -DNEXOBS=3 -DSVR_REUSEADDR")

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -O3 -ansi -pedantic ")

if ("${CMAKE_C_COMPILER_ID}" STREQUAL "GNU" OR
    "${CMAKE_C_COMPILER_ID}" STREQUAL "Clang")

    set(warnings "-Wall -Wno-unused-but-set-variable")
elseif ("${CMAKE_C_COMPILER_ID}" STREQUAL "MSVC")
    set(warnings "/W4 /WX /EHsc")
else()
    message(WARNING "unknown CMAKE_C_COMPILER_ID=${CMAKE_C_COMPILER_ID}")
endif()

find_library(m rt pthread)

include_directories(. "${SRC_DIR}")
# file(GLOB RTKLIB_RCV_SRC "src/rcv/*.c")
file(GLOB RTKLIB_SRC "src/*.c" "src/rcv/*.c")

# TODO: some bug compiling these
# needs showmsg + something else
list(REMOVE_ITEM RTKLIB_SRC 
    "${CMAKE_CURRENT_SOURCE_DIR}/src/postpos.c" 
    "${CMAKE_CURRENT_SOURCE_DIR}/src/convrnx.c"
    "${CMAKE_CURRENT_SOURCE_DIR}/src/download.c")

# message("asdf ${RTKLIB_SRC}")
add_library(rtklib_obj OBJECT ${RTKLIB_SRC})
# TARGET_LINK_LIBRARIES(rtklib_obj
#     pthread m rt
# )


add_subdirectory(app)
