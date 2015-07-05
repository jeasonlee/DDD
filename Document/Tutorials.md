# 教程列表

🕐**015mins** 为教程的阅读时间，
如附带操作测试和拓展则需更不可估计的时间。


## VPS 相关

### 添加与使用 SSH

 🕐**015mins** [添加与使用 SSH](https://www.digitalocean.com/community/tutorials/how-to-use-ssh-keys-with-digitalocean-droplets)

```bash
vim /etc/ssh/sshd_config

# 仅可使用 SSH 登陆

PermitRootLogin without-password

# ps auxw | grep ssh
USER       PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root       681  0.0  0.1  49948  2332 ?        Ss    2012   3:23 /usr/sbin/sshd -D

# kill -HUP 681
```

## Linux 相关

### 设置系统 Swap 文件

🕐**005mins** [设置系统 Swap 文件](https://meta.discourse.org/t/create-a-swapfile-for-your-linux-server/13880)

```bash
sudo install -o root -g root -m 0600 /dev/null /swapfile
dd if=/dev/zero of=/swapfile bs=1k count=2048k
mkswap /swapfile
swapon /swapfile
echo "/swapfile       swap    swap    auto      0       0" | sudo tee -a /etc/fstab
sudo sysctl -w vm.swappiness=10
echo vm.swappiness = 10 | sudo tee -a /etc/sysctl.conf
```

## Discourse 相关

### 安装 Discourse

🕐**030mins** [快速 Docker 安装](https://github.com/discourse/discourse/blob/master/docs/INSTALL-cloud.md)
