
set(convbin_sources "convbin.c"
    ${SRC_DIR}/rtkcmn.c
    ${SRC_DIR}/rinex.c
    ${SRC_DIR}/sbas.c
    ${SRC_DIR}/preceph.c
    ${SRC_DIR}/rcvraw.c
    
    ${SRC_DIR}/convrnx.c

    ${SRC_DIR}/rtcm.c
    ${SRC_DIR}/rtcm2.c
    ${SRC_DIR}/rtcm3.c
    ${SRC_DIR}/rtcm3e.c
    ${SRC_DIR}/pntpos.c
    ${SRC_DIR}/ionex.c
    ${SRC_DIR}/ephemeris.c
    ${SRC_DIR}/qzslex.c
)

add_executable(convbin ${convbin_sources} ${RTKLIB_RCV_SRC})
# add_dependencies(rtkrcv rtklib_obj)
TARGET_LINK_LIBRARIES(convbin
    m rt
)


install(TARGETS convbin DESTINATION bin)