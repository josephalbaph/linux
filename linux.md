```
useradd -m -s /bin/bash -G sudo djangoapp
passwd djangoapp
groups djangoapp
su djangoapp
sudo hostnamectl set-hostname salemcsi
bash

ssh-keygen -f ~/.ssh/djangoapp
ssh-copy-id -i ~/.ssh/djangoapp djangoapp@salemcsi.cf
```
edit sshd_config
```
sudo nano /etc/ssh/sshd_config
PermitRootLogin no 
PubkeyAuthentication yes
PasswordAuthentication no


sudo systemctl restart sshd
```

nginx
```
sudo wget https://nginx.org/keys/nginx_signing.key
sudo apt-key add nginx_signing.key

sudo nano /etc/apt/sources.list
deb https://nginx.org/packages/mainline/ubuntu/ bionic nginx
deb-src https://nginx.org/packages/mainline/ubuntu/ bionic nginx

sudo nano /etc/apt/sources.list.d/nginx.list
deb [arch=amd64] http://nginx.org/packages/ubuntu/ bionic nginx
deb-src http://nginx.org/packages/ubuntu/ bionic nginx

sudo apt-get install nginx
```
install acl
```
sudo apt install acl
```
assign rights to user
```
sudo setfacl -m u:djangoapp:rwx /etc/nginx/*
sudo setfacl -m u:djangoapp:rwx /etc/nginx/conf.d/*
```
