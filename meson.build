project('rtklib', 'c',
	version: 'git',
	meson_version: '>=0.45.0')

git_exe = find_program('git')

# Get version_commit
version_commit = run_command(git_exe, '-C', repo, 'rev-list', '--all', '--count')
if version_commit.returncode() != 0
  version_commit = 0
else
  version_commit = version_commit.stdout().strip()
endif

platform_deps = []
platform_inc = ['.', 'src']

if host_machine.system() == 'windows'
  platform_deps = [cc.find_library('ws2_32')]
  platform_inc += ['libr/include/msvc']
endif
platform_inc = include_directories(platform_inc)


add_global_arguments('-Wall', '-O3', '-ansi', '-pedantic', '-Wno-unused-but-set-variable', language: 'c')
add_global_arguments('-DENAGLO', '-DENAQZS', '-DENACMP', '-DENAGAL', '-DENAIRN', '-DNFREQ=3', '-DSVR_REUSEADDR', language: 'c')

cc = meson.get_compiler('c')

core_deps = [cc.find_library('m', required: false),
	cc.find_library('rt', required: false),
	cc.find_library('pthread', required: false)]

subdir('src')
subdir('app')




install_subdir('data', install_dir : join_paths(get_option('prefix'), get_option('datadir'), 'rtklib'))
