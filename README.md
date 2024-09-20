# Docker_WordPress

在CMD下載 MariaDB `docker pull mariadb:10.6.19-focal` 
<br>
在CMD下載 WordPress `docker pull wordpress:6.6.2-apache`
<br>
更新任何configure files必須重啟docker `docker compose down` -> `docker compose up`
<br>
wp-config.php中，要改你phpadmin user name & password，他們在.env的檔案中，你自己設定的
```
// ** Database settings - You can get this info from your web host ** //
/** The name of the database for WordPress */
define( 'DB_NAME', getenv_docker('WORDPRESS_DB_NAME', 'wordpress') );

/** Database username */
define( 'DB_USER', getenv_docker('WORDPRESS_DB_USER', 'example username') );

/** Database password */
define( 'DB_PASSWORD', getenv_docker('WORDPRESS_DB_PASSWORD', 'example password') );

/**
 * Docker image fallback values above are sourced from the official WordPress installation wizard:
 * https://github.com/WordPress/WordPress/blob/1356f6537220ffdc32b9dad2a6cdbe2d010b7a88/wp-admin/setup-config.php#L224-L238
 * (However, using "example username" and "example password" in your database is strongly discouraged.  Please use strong, random credentials!)
 */

/** Database hostname */
define( 'DB_HOST', getenv_docker('WORDPRESS_DB_HOST', 'mysql') ); /*msql 改成 databases:3306*/

```
