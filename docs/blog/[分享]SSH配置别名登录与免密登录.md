0. 环境
服务器：CentOS 7.2
客户端：MacOS 10.15.3

1. 配置客户端SSH登录别名：
```
# 修改 ssh_config 文件
sudo vim /etc/ssh/ssh_config
# 添加服务器别名
Host server_name                    // 服务器别名
    HostName 49.110.210.150         // 服务器公网地址
    User root                       // 服务器登录账号
```
```
# 使用：
ssh server_name     // server_name为上面配置的别名
```

3. SSH免密登陆
``` 
# 客户端终端
cd ~/.ssh  // 更换目录到 ~/.ssh
ssh-keygen // 一路回车确认后生成公私钥对
ls  // 查看生成的公私钥文件 => id_rsa, id_rsa.pub

# 发送公钥到服务器
ssh-copy-id -i id_rsa.pub 服务器账号@服务器地址 // 例：ssh-copy-id -i id_rsa.pub root@49.110.210.150

# 免密登录
ssh server_name // 连接登录服务器

```

4. 禁用密码登录
```
# 服务器终端
vim /etc/ssh/ssh_config
// 禁用密码登录
Host *
  PasswordAuthentication no
```
