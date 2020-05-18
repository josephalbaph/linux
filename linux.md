useradd -m -s /bin/bash -G sudo djangoapp
passwd djangoapp
groups djangoapp
su djangoapp
sudo hostnamectl set-hostname salemcsi
bash

ssh-keygen -f ~/.ssh/djangoapp
ssh-copy-id -i ~/.ssh/djangoapp djangoapp@salemcsi.cf
/usr/bin/ssh-copy-id: INFO: Source of key(s) to be installed: "/home/djangoapp/.ssh/djangoapp.pub"
The authenticity of host 'salemcsi.cf (47.57.75.42)' can't be established.
ECDSA key fingerprint is SHA256:XAC01n+0hsWlmZHH9MBSgGTCYoVn6O+P8O1Q531+Mvs.
Are you sure you want to continue connecting (yes/no)? yes
/usr/bin/ssh-copy-id: INFO: attempting to log in with the new key(s), to filter out any that are already installed
/usr/bin/ssh-copy-id: INFO: 1 key(s) remain to be installed -- if you are prompted now it is to install the new keys
djangoapp@salemcsi.cf's password: 

Number of key(s) added: 1

Now try logging into the machine, with:   "ssh 'djangoapp@salemcsi.cf'"
and check to make sure that only the key(s) you wanted were added.

