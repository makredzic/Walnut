project(
    'Walnut',
    'cpp',
    version : '1.0',
    default_options : ['warning_level=3', 'cpp_std=c++17', 'optimization=2', 'default_library=static'],
)

source_files = [] # this variable is populated by nested meson.build files in the src/ dir
subdir('src')

include = include_directories('include')

walnut_dep = declare_dependency(
    include_directories: include,
    link_with: library(
      'walnut', 
      sources: source_files,
      include_directories: include,
      dependencies: [
        dependency('threads'),
        dependency('glfw3'),
        dependency('glm'),
        dependency('imgui'),
        meson.get_compiler('cpp').find_library('vulkan', dirs: '/home/mredzic/vulkan/1.3.296.0/x86_64/lib') # returns a dep object
      ]
    )
)