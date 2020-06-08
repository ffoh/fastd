project(
	'fastd',
	'c',
	version : '19+',
	default_options : [ 'c_std=c99', 'warning_level=2' ],
	meson_version: '>=0.49',
)

subdir('src')


clang_format = find_program(
	'clang-format',
	required : false,
	disabler : true,
)

custom_target(
	'format',
	build_by_default : false,
	build_always_stale : true,
	output: ['format'],
	command : [
		'sh',
		'-c',
		'cd "$1" && find src -type f -name "*.[ch]" | xargs "$2" -i --style=file',
		'-',
		meson.current_source_dir(),
		clang_format,
	],
)