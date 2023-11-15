project('cjson', 'c')

clib = meson.get_compiler('c').find_library('c', required: false)
clib_dep = []
if not clib.found()
	clib_dep = dependency('libc', fallback: ['libc', 'libc_dep'], required: true)
endif

cjson_sources = [
    'cJSON.c',
    'cJSON_Utils.c',
]

cjson_inc = include_directories('.', '.')

cjson_lib = library('cjson',
	sources: [cjson_sources],
	include_directories : cjson_inc,
	dependencies : [clib_dep],
	install : false
)

cjson_dep = declare_dependency(include_directories : cjson_inc, link_with : cjson_lib)
