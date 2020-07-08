# gitbook安装手册

### 一、安装Node.js

- 版本大于4.0.0

```bash
# 获取noode.js安装包
[root@test1 ~]# wget https://nodejs.org/dist/v7.7.1/node-v7.7.1-linux-x64.tar.xz

# 解压
[root@test1 ~]# tar -xvf node-v7.7.1-linux-x64.tar.xz

# 重命名
[root@test1 ~]# mv node-v7.7.1-linux-x64 nodejs

# 创建软连接
[root@test1 ~]# ln -s /root/nodejs/bin/npm /usr/local/bin/
[root@test1 ~]# ln -s /root/nodejs/bin/node /usr/local/bin/

# 检查
[root@test1 nodejs]# node -v
v7.7.1
```

### 二、安装gitbook

```bash
[root@test1 nodejs]# npm install gitbook-cli -g
/root/nodejs/bin/gitbook -> /root/nodejs/lib/node_modules/gitbook-cli/bin/gitbook.js
/root/nodejs/lib


# 配置环境变量
[root@test1 ~]# cat .bash_profile
# .bash_profile

# Get the aliases and functions
if [ -f ~/.bashrc ]; then
    . ~/.bashrc
fi

# User specific environment and startup programs

PATH=$PATH:$HOME/bin:/root/nodejs/bin

export PATH

[root@test1 ~]# source .bash_profile

# 检查是否安装成功
[root@test1 ~]# gitbook -V
CLI version: 2.3.2
Installing GitBook 3.2.3
/root/nodejs/lib/node_modules/gitbook-cli/node_modules/npm/node_modules/graceful-fs/polyfills.js:287
      if (cb) cb.apply(this, arguments)
                 ^

TypeError: cb.apply is not a function
    at /root/nodejs/lib/node_modules/gitbook-cli/node_modules/npm/node_modules/graceful-fs/polyfills.js:287:18

# 如果出现上面情况(一般是nodejs的版本问题，建议降低nodejs版本)
[root@test1 ~]# gitbook -V
CLI version: 2.3.2
GitBook version: 3.2.3
```
