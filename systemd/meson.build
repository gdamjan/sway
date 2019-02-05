systemd_dep = dependency('systemd')

if systemd_dep.found()
  user_units_dir = systemd_dep.get_pkgconfig_variable('systemduserunitdir')

  configure_file(
    configuration: config,
    input: 'sway.service.in',
    output: '@BASENAME@',
    install_dir: user_units_dir
  )
  install_data('sway-session.target',
      install_dir: user_units_dir)
  install_data('10-systemd',
      install_dir: join_paths(sysconfdir, 'sway/config.d'))
  install_data('sway-service.desktop',
      install_dir: join_paths(datadir, 'wayland-sessions'))
  install_data('sway-service.sh',
      install_dir: join_paths(prefix, 'bin'))

endif
