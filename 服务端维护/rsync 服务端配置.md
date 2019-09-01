## rsync 服务端配置

* yum 安装 rsync:

```
yum -y install rsync
```

-y 参数的含义是, 全部问题自动回答 yes.


* 配置 rsync 上传目录:

```
vim /etc/rsyncd.conf
```

加入如下内容:

```
[documents]
path = /root/wwwroot
list = true
read only = false
uid = root
gid = root
```


* 管理 rsync 进程, 通过 xinetd

```
yum install -y xinetd
```

配置 xinetd

```
vim /etc/xinetd.d/rsync 
```

```
service rsync
{
 disable  = no
 flags  = IPv6
 socket_type     = stream
 wait            = no
 user            = root
 server          = /usr/bin/rsync
 server_args     = --daemon
 log_on_failure  += USERID
}
```

启动 xinet 服务

```
systemctl start xinetd.service
systemctl enable xinetd.service
```


* 打开防火墙端口, 否则会连接不上

```
firewall-cmd --permanent --add-port=873/tcp
```

重新加载

```
firewall-cmd --reload
```

列出端口

```
firewall-cmd --list-ports
```