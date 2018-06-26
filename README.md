# ansible-vivo

## Server Variables

- `vivo_domain`: The hostname of the VIVO server.

- `vivo_admin_email`: The email address of the VIVO admin user.

## Database Variables

- `vivo_db_name`: The name of the database that VIVO will use.
  Defaults to `vivo_db`.

- `vivo_db_user`: The name of the user that VIVO will use to connect
  to the database.  Defaults to `vivo_user`.

- `vivo_db_pass`: The password for the `vivo_db_user`.

- `vivo_db_type`: The database being used for VIVO.  Defaults to
  `mysql`, can also be `postgresql`.

## Other Variables

- `app_name`: The display name of the application.  Defaults to “vivo”.

- `tomcat_home_path`: The location of your Tomcat installation.
  Defaults to `/usr/share/tomcat`.

- `vitro_commit`: The Git SHA for the version of Vitro to install.
  Defaults to the 1.9.3 release, `903cc232b477a7aeb2043623dfd174d0fd7734ab`

- `vitro_build_path`: The location to clone Vitro to; defaults to `/opt/Vitro`

- `vivo_commit`: The Git SHA for the version of Vitro to install.
  Defaults to the 1.9.3 release, `37cc07263bfa3010415d386b220a6340874fed32`

- `vivo_build_path`: The location to clone VIVO to; defaults to `/opt/VIVO`

- `vivo_home_path`: The location of the VIVO home directory; defaults
  to `/usr/local/vivo/home`.
