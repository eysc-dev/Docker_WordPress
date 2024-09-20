# Docker_WordPress

在CMD下載 MariaDB `docker pull mariadb:10.6.19-focal` 
<br>
在CMD下載 WordPress `docker pull wordpress:6.6.2-apache`
<br><br>
更新任何configure files必須重啟docker `docker compose down` -> `docker compose up`
<br><br>
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

要將本地檔案上傳到 GitHub，你可以按照以下步驟操作：

1. 打開終端機或命令提示字元，導航到你的專案目錄，然後執行以下命令來初始化 Git 儲存庫：
     ```
     git init
     ```

2. 將所有檔案新增到 Git 儲存庫中：
     ```bash
     git add .
     ```

3. 提交變更並添加提交訊息：
     ```
     git commit -m "Initial commit"
     ```

4. 將你的本地儲存庫連接到 GitHub 上的遠端儲存庫。假設你的遠端儲存庫 URL 是 `https://github.com/yourusername/your-repo.git`，你可以使用以下命令：
     ```
     git remote add origin https://github.com/yourusername/your-repo.git
     ```

5. 將本地儲存庫的變更推送到 GitHub 上的遠端儲存庫：
     ```
     git push -u origin main
     ```

