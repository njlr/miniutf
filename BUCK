genrule(
  name = 'miniutfdata',
  out = 'miniutfdata.h',
  srcs = glob([
    'preprocess.py',
    'data-6.3.0/*.txt',
  ]),
  cmd = 'python preprocess.py > $OUT',
)

cxx_library(
  name = 'miniutf',
  header_namespace = '',
  exported_headers = subdir_glob([
    ('', '*.hpp'),
    ('', '*.h'),
  ]),
  srcs = glob([
    '*.cpp',
  ], excludes = [
    'test.cpp',
  ]),
  licenses = [
    'LICENSE.txt',
  ],
  visibility = [
    'PUBLIC',
  ],
)

cxx_binary(
  name = 'test',
  srcs = [
    'test.cpp',
  ],
  deps = [
    ':miniutf',
  ],
)
