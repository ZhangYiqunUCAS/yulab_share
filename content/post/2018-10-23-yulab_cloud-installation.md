---
title: "NextCloud Installation"
date: 2018-10-19T01:05:14+08:00
draft: false
tags: ["yulab_cloud"]

---


## NextCloud管理

### 用户管理

+ 增加\删除用户

使用管理员账号登录网页，`设置->用户` 进行相关操作。

<!--more-->

+ 禁用\开启 用户

```
$ sudo -u www-data php occ user:disable <username>
$ sudo -u www-data php occ user:enable <username>
```

+ 找回管理员密码

```
$ sudo -u www-data php /var/www/nextcloud/occ user:resetpassword admin
```

+ 恢复被误删的文件

```
$ 
```

+ Backup and Recover

data files, MySQL, configuration files

```

```






测试环境：`Ubuntu 18.04 LTS`

## 安装方法

### 1. `snap`一步法 （我没有使用）

该方法见`ubuntu`，我暂时不推荐，我打算使用更加自由的安装方法。

```
$ sudo snap install nextcloud
```

<!--more-->

### 2. LAMP + NextCloud (推荐）

+ 安装 LAMP

NextCloud需要使用`Apache2`的web服务和`MySQL|MariaDB`提供的数据库服务，已经`PHP`.

```
$ sudo apt-get install apache2 mariadb-server libapache2-mod-php7.2
$ sudo apt-get install php7.2-gd php7.2-json php7.2-mysql php7.2-curl php7.2-mbstring
$ sudo apt-get install php7.2-intl php-imagick php7.2-xml php7.2-zip
```

+ 安装NextCloud

从官网下载 `nextcloud-x.y.z.tar.bz2`  
`Download Nextcloud Server > Download > Archive file for server owners `

解压并安装：

```
$ tar -jxf nextcloud-x.y.z.tar.bz2
$ sudo cp -r nextcloud /var/www/
```

+ 配置LAMP

创建configure文档，`/etc/apache2/sites-available/nextcloud.conf`
填入以下内容：

```
Alias /nextcloud "/var/www/nextcloud/"

<Directory /var/www/nextcloud/>
  Options +FollowSymlinks
  AllowOverride All

 <IfModule mod_dav.c>
  Dav off
 </IfModule>

 SetEnv HOME /var/www/nextcloud
 SetEnv HTTP_HOME /var/www/nextcloud

</Directory>
```

然后应用这个配置文件

```
$ sudo a2ensite nextcloud.conf
```

还需要其他mod

```
$ sudo a2enmod rewrite
$ sudo a2enmod headers
$ sudo a2enmod env
$ sudo a2enmod dir
$ sudo a2enmod mime
```

重启`Apache`服务

```
$ sudo service apache2 restart
```

+ 配置NextCloud

使用命令行安装的方法比较简单：

```
$sudo chown -R www-data:www-data /var/www/nextcloud/ # 修改网站路径下的文件权限

$ cd /var/www/nextcloud/
$ sudo -u www-data php occ maintenance:install --database "mysql" --database-name "nextcloud"  --database-user "root" --database-pass "password" --admin-user "admin" --admin-pass "password"
```

通常到此为止，NextCloud服务已经正常开启。可以访问https://localhost/nextcloud进行访问和更多设置。

相关链接：  

[Install on Linux](https://docs.nextcloud.com/server/14/admin_manual/installation/source_installation.html#pretty-urls-label)

[命令行安装NextCloud](https://docs.nextcloud.com/server/14/admin_manual/installation/command_line_installation.html)








