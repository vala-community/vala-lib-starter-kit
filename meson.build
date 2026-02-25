project('${LIBRARY_NAME}', 'vala', 'c',
  version: '${PROJECT_VERSION}',
  meson_version: '>= 1.1.0',
  default_options: [
    'warning_level=2',
    'werror=false',
  ],
)

LIBRARY_NAME = meson.project_name()
GIR_NAME = '${GIR_NAME}'
PROJECT_DESCRIPTION = '${PROJECT_SUMMARY}'
PROJECT_VERSION = meson.project_version()
API_VERSION = '${API_VERSION}'

pkgconfig = import('pkgconfig')
PKGCONFIG_DEPS = ['glib-2.0', 'gobject-2.0']
OBJECT_PATH = '${OBJECT_PATH}'

vapidir = get_option('datadir') / 'vala' / 'vapi'

g_ir_compiler = find_program('g-ir-compiler', required: false)

${LIBRARY_DEP_NAME}_deps = [
  dependency('glib-2.0'),
  dependency('gobject-2.0')
]

config_data = configuration_data()
config_data.set('OBJECT_PATH', OBJECT_PATH)
config_file = configure_file(
  input: 'src/Config.vala.in',
  output: '@BASENAME@',
  configuration: config_data,
)

subdir('src')
subdir('tests')
subdir('docs')
