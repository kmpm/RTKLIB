install_headers('rtklib.h')

#common rtklib sources
rtklib_sources = ['geoid.c', 'preceph.c', 'rcvraw.c', 
	'rtcm.c', 'rtcm2.c', 'rtcm3.c', 'rtcm3e.c', 'rtkcmn.c', 
	'sbas.c', 'solution.c', 'stream.c']

# common rcv sources
rtklib_rcv_sources = ['rcv/novatel.c', 'rcv/ublox.c', 'rcv/ss2.c', 'rcv/crescent.c',
	'rcv/skytraq.c', 'rcv/gw10.c', 'rcv/javad.c', 'rcv/nvs.c', 
	'rcv/binex.c', 'rcv/rt17.c', 'rcv/septentrio.c', 'rcv/cmr.c', 'rcv/tersus.c']


# rtkrcv unique sources
rtkrcv_src_sources = ['ephemeris.c', 'ionex.c', 'lambda.c',  'options.c', 
	'pntpos.c', 'ppp.c', 'ppp_ar.c', 'ppp_corr.c', 'rinex.c', 'rtkpos.c', 'rtksvr.c',  
	'tides.c', 'qzslex.c']

# str2str unique sources
str2str_src_sources = ['streamsvr.c']

# concatenate them all
rtklib_sources += rtklib_rcv_sources
rtklib_sources += rtkrcv_src_sources
rtklib_sources += str2str_src_sources


# build rtklib as static_library
rtklib = static_library('rtklib',rtklib_sources,
	dependencies: core_deps)
