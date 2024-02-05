# 🐳 Docker + PHP 8.2 + MySQL + PgSql + Nginx + Symfony 7.0.3 Boilerplate

## Description

This is a complete stack for running Symfony 7.0.3 into Docker containers using docker-compose tool.

It is composed by 4 containers:

- `nginx`, acting as the webserver.
- `php-fpm`, the PHP-FPM container with the 8.2 version of PHP.
- `mysql` which is the MySQL database container with a **MySQL 8.0** image.
- `pgsql` which is the MySQL database container with a **Postgres 16** image.

## Installation

1. Clone this repo.

2. If you are working with Docker Desktop for Mac, ensure **you have enabled `VirtioFS` for your sharing implementation**. `VirtioFS` brings improved I/O performance for operations on bind mounts. Enabling VirtioFS will automatically enable Virtualization framework.

3. Create the file `./.docker/.env.nginx.localhost` using `./.docker/.env.nginx` as template. The value of the variable `NGINX_BACKEND_DOMAIN` is the `server_name` used in NGINX.

4. Go inside folder `./docker` and run `docker compose up -d` to start containers.

5. You should work inside the `php-fpm` container. This project is configured to work with [Remote Container](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-containers) extension for Visual Studio Code, so you could run `Reopen in container` command after open the project.

6. Use the following value for the DATABASE_URL environment variable:

```
DATABASE_URL=mysql://app_user:app_password@db:3306/app_db?serverVersion=8.0.33
```
or 
```
DATABASE_URL=postgres://app_user:app_password@app_:5432/app_db?serverVersion=16
```
