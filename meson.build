project('csptr', 'c',
    version: '2.0.5-7'
)

config = configuration_data()
config.set('PROJECT_NAME', 'csptr')
config.set('PROJECT_VERSION', '2.0.5-7')
config.set10('SMALLOC_FIXED_ALLOCATOR', false)
config.set10('CSPTR_NO_SENTINEL', false)

config_h = configure_file(input: 'src/config.h.in',
    output: 'config.h',
    configuration: config,
    format: 'cmake')

csptr_inc = include_directories('include/csptr')
csptr_src = include_directories('src')
csptr_lib = shared_library('csptr',
    'src/array.c',
    'src/mman.c',
    include_directories: [csptr_inc, csptr_src]
)

csptr_dep = declare_dependency(link_with: csptr_lib,
    include_directories: csptr_inc)
