## 安装 NodeJS

*包管理安装
```
yum install -y gcc-c++ make
curl -sL https://rpm.nodesource.com/setup_10.x | sudo -E bash -
```

```
yum install nodejs
```


*直接编译安装
下载

```
wget https://nodejs.org/dist/latest-v10.x/node-v10.16.3.tar.gz
```

解压

```
tar xzvf node-v* && cd node-v*
```

安装依赖库
```
sudo yum install -y gcc gcc-c++
```

make

```
./configure
make
```

安装
```
sudo make install
```

查看版本

```
node --version
```