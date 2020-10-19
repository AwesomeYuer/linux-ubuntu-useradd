# linux-ubuntu-useradd

服务器端主机
```shell
# 非交互式使用 sh 终端提示符
sudo useradd user01 -m

# 设置密码
sudo passwd user01

# 删除用户
sudo userdel -r user01

```




交互式创建用户: user01
```shell
sudo adduser user01
```

将新建用户添加到 sudoers file
/etc/sudoers
```shell
user01   ALL=(ALL) ALL
```



免密登陆

1. 在客户端 Linux 主机
```shell
# Generating public/private rsa key pair.
ssh-keygen -t rsa

# 打印公钥文件
cat ~/.ssh/id_rsa.pub

# 打印公钥文件
cat ~/.ssh/id_rsa

# 公钥上传到远程登录服务器
ssh-copy-id -i ~/.ssh/id_rsa.pub -p 22 user01@192.168.137.100
```

2. 在服务器端 Linux 主机
```shell
# 打印免密登录用户的授权 authorized_keys 文件
cat ~/.ssh/authorized_keys
```
