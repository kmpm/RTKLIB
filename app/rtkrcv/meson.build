
rtkrcv_sources = ['rtkrcv.c', 'vt.c']

install_headers('vt.h')

executable('rtkrcv', rtkrcv_sources,
	include_directories : inc,
	link_with: rtklib,
	dependencies: core_deps)
