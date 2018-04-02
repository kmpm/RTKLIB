
set(str2str_sources "str2str.c"
    # ${SRC_DIR}/stream.c
    # ${SRC_DIR}/streamsvr.c
    # ${SRC_DIR}/rtkcmn.c
    # ${SRC_DIR}/solution.c
    # ${SRC_DIR}/sbas.c
    # ${SRC_DIR}/geoid.c
    # ${SRC_DIR}/rcvraw.c
    # ${SRC_DIR}/rtcm.c
    # ${SRC_DIR}/rtcm2.c
    # ${SRC_DIR}/rtcm3.c
    # ${SRC_DIR}/rtcm3e.c
    # ${SRC_DIR}/preceph.c
)

add_executable(str2str ${str2str_sources} $<TARGET_OBJECTS:rtklib_obj>)
# add_dependencies(str2str rtklib_obj)
TARGET_LINK_LIBRARIES(str2str
    m rt pthread
)


install(TARGETS str2str DESTINATION bin)