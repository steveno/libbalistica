vala_args = [ 
  '--target-glib', glib_min_version,
  '--enable-checking',
]

lib_sources = files([
  'Atmosphere.vala',
  'FreeRecoil.vala',
  'Greenhill.vala',
  'LibBalistica.vala',
  'Miller.vala',
  'Pbr.vala',
  'Retard.vala',
  'SectionalDensity.vala',
  'Solution.vala',
  'Solve.vala',
  'Thornhill.vala',
  'Windage.vala',
  'Zero.vala',
  'conversion/Mass.vala',
  'conversion/Angle.vala',
  'conversion/Temperature.vala'
])

libbalistica = shared_library ( 'balistica',
  lib_sources,
  version: meson.project_version(),
  vala_gir: meson.project_name() + '-' + meson.project_version() + '.gir',
  vala_vapi: meson.project_name() + '.vapi',
  vala_header: meson.project_name() + '.h',
  dependencies: [ glib_dep, gee_dep ],
  c_args: [ '-g' ],
  link_args: ['-lm'],
  install: true,
  install_dir: [true, true, true, true],
)

pkg.generate(
  libraries: libbalistica,
  version: meson.project_version(),
  name: meson.project_name(),
  description: 'Open soure ballistics library written in Vala',
  requires: [
    'glib-2.0',
    'gobject-2.0',
    'gee-0.8',
  ],
)

lib_dep = declare_dependency(
    sources: lib_sources
)
