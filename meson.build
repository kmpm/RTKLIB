project('rtklib', 'c',
	version: 'git')

inc = include_directories('src')

add_global_arguments('-Wall', '-O3', '-ansi', '-pedantic', '-Wno-unused-but-set-variable', language: 'c')
add_global_arguments('-DENAGLO', '-DENAQZS', '-DENACMP', '-DENAGAL', '-DENAIRN', '-DNFREQ=3', '-DSVR_REUSEADDR', language: 'c')

core_deps = [find_library('m', required: false),
	find_library('rt', required: false),
	find_library('pthread', required: false)]

subdir('src')
subdir('app')

