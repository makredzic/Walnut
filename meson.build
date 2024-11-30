project(
    'Walnut',
    'cpp',
    version : '1.0',
    default_options : ['warning_level=3', 'cpp_std=c++17', 'optimization=2', 'default_library=static'],
)

source_files = [] # this variable is populated by nested meson.build files in the src/ dir
subdir('src')

include = include_directories('include')


cpp = meson.get_compiler('cpp')
vulkan_lib_dir= '/home/mredzic/vulkan/1.3.296.0/x86_64/lib'
vulkan_dep= cpp.find_library('vulkan', dirs: vulkan_lib_dir)


imgui_dep = dependency('imgui')

deps = [
  dependency('threads'),
  dependency('glfw3'),
  dependency('glm'),
  imgui_dep,
  vulkan_dep
]

walnut_dep = declare_dependency(
    include_directories: include,
    link_with: library(
      'walnut', 
      sources: source_files,
      include_directories: include,
      dependencies: deps
    )
)