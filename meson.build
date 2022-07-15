project('roaring', 'c')

roaring_c_args = ['-Wall', '-Wextra', '-Wsign-compare',
  '-Wshadow', '-Wwrite-strings', '-Wpointer-arith', '-Winit-self']

if host_machine.cpu_family() == 'arm' or host_machine.cpu_family() == 'aarch64'
roaring_c_args += ['-DDISABLEAVX']
else
roaring_c_args = ['-march=native']
endif

includes = include_directories(['include'])

libroaring = library('roaring',
  'src/array_util.c',
  'src/bitset_util.c',
  'src/containers/array.c',
  'src/containers/bitset.c',
  'src/containers/containers.c',
  'src/containers/convert.c',
  'src/containers/mixed_intersection.c',
  'src/containers/mixed_union.c',
  'src/containers/mixed_equal.c',
  'src/containers/mixed_subset.c',
  'src/containers/mixed_negation.c',
  'src/containers/mixed_xor.c',
  'src/containers/mixed_andnot.c',
  'src/containers/run.c',
  'src/memory.c',
  'src/roaring.c',
  'src/roaring_priority_queue.c',
  'src/roaring_array.c',
  implicit_include_directories : false,
  include_directories: [includes])

roaring_dep = declare_dependency(
  link_with: libroaring,
  include_directories: [includes])
