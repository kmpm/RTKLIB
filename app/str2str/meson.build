str2str_sources = ['str2str.c']

executable('str2str', str2str_sources,
	c_args : '-DNEXOBS=3', 
	
	include_directories : inc,
	link_with: rtklib,
	dependencies: core_deps)