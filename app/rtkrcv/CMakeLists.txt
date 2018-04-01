
set(rtkrcv_sources "rtkrcv.c" "vt.c"
    ${SRC_DIR}/rtkcmn.c
    ${SRC_DIR}/rtksvr.c
    ${SRC_DIR}/rtkpos.c
    ${SRC_DIR}/geoid.c
    ${SRC_DIR}/solution.c
    ${SRC_DIR}/lambda.c
    ${SRC_DIR}/sbas.c
    ${SRC_DIR}/stream.c
    ${SRC_DIR}/rcvraw.c
    ${SRC_DIR}/rtcm.c
    ${SRC_DIR}/rtcm2.c
    ${SRC_DIR}/rtcm3.c
    ${SRC_DIR}/rtcm3e.c
    ${SRC_DIR}/preceph.c
    ${SRC_DIR}/options.c
    ${SRC_DIR}/pntpos.c
    ${SRC_DIR}/ppp.c
    ${SRC_DIR}/ppp_ar.c
    ${SRC_DIR}/ephemeris.c
    ${SRC_DIR}/rinex.c
    ${SRC_DIR}/ionex.c
    ${SRC_DIR}/qzslex.c
    ${SRC_DIR}/tides.c
    ${SRC_DIR}/ppp_corr.c
    )
add_executable(rtkrcv ${rtkrcv_sources} ${RTKLIB_RCV_SRC})
# add_dependencies(rtkrcv rtklib_obj)
TARGET_LINK_LIBRARIES(rtkrcv
    pthread m rt
)

install(TARGETS rtkrcv DESTINATION bin)