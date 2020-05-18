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
sudo systemctl status nginx

