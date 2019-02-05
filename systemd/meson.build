systemd_dep = dependency('systemd')

if systemd_dep.found()
  user_units_dir = systemd_dep.get_pkgconfig_variable('systemduserunitdir')

  configure_file(
    configuration: config,
    input: 'sway.service.in',
    output: '@BASENAME@',
    install_dir: user_units_dir
  )

  systemd_units = files(
    'sway-session.target',
  )
  install_data(systemd_units, install_dir: user_units_dir)


  sway_systemd_scripts = files(
    '10-systemd',
  )

  install_data(sway_systemd_scripts, install_dir: sysconfdir + '/sway/config.d')
endif
