project('rtklib', 'c',
	version: 'git')

inc = include_directories('src')

add_global_arguments('-Wall', '-O3', '-ansi', '-pedantic', '-Wno-unused-but-set-variable', language: 'c')
add_global_arguments('-DENAGLO', '-DENAQZS', '-DENACMP', '-DENAGAL', '-DENAIRN', '-DNFREQ=3', '-DSVR_REUSEADDR', language: 'c')

cc = meson.get_compiler('c')

core_deps = [cc.find_library('m', required: false),
	cc.find_library('rt', required: false),
	cc.find_library('pthread', required: false)]

subdir('src')
subdir('app')

