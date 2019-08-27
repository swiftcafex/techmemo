## 设置 SSH 超时时间

vim 打开配置文件:

```
vim /etc/ssh/sshd_config 
```

加入这两个设置项:

```
ClientAliveInterval 120
ClientAliveCountMax 720
```