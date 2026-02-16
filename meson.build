project(
    'bikramsambat',
    'c',
    version: '1.1.1',
    default_options: [
        'c_std=c99',
        'warning_level=3',
        'werror=true',
        'buildtype=debug',
        'b_lundef=false',
        'b_sanitize=address,undefined',
    ],
)

cc = meson.get_compiler('c')

add_project_arguments('-D_POSIX_C_SOURCE=200809L', language: 'c')
add_project_link_arguments('-lm', '-pthread', language: 'c')

extra_warnings = [
    '-Wshadow',
    '-Wformat=2',
    '-Wconversion',
    '-Wsign-conversion',
    '-Wnull-dereference',
    '-Wdouble-promotion',
    '-Wstrict-prototypes',
    '-Wmissing-prototypes',
    '-Wold-style-definition',
    '-Wbad-function-cast',
    '-Wcast-align',
    '-Wcast-qual',
    '-Wfloat-equal',
    '-Wswitch-default',
    '-Wswitch-enum',
    '-Wundef',
    '-Wpointer-arith',
    '-Wvla',
    '-Wwrite-strings',
]

foreach warning : extra_warnings
    if cc.has_argument(warning)
        add_project_arguments(warning, language: 'c')
    endif
endforeach

sources = files('src/main.c')
bs = executable('bikramsambat', sources, install: true)
