## 安装 mysql

```
yum install -y mariadb-server
yum install -y mariadb
```


开启并注册服务

```
systemctl start mariadb
systemctl enable mariadb
```


设置管理密码

```
SET PASSWORD FOR 'user-name-here'@'hostname' = PASSWORD('new-password’);
```

创建数据库注意:

```
CREATE DATABASE qimage_test CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```
* utf8mb4: A UTF-8 encoding of the Unicode character set using one to four bytes per character.
* utf8mb3: A UTF-8 encoding of the Unicode character set using one to three bytes per character.