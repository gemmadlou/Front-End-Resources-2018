# Ubuntu 16.04 MySQL Setup

TLDR

```
# 1) Setup droplet (in digitalocean or by other means eg. Terraform, the API)

# 2) SSH IN
ssh root@HOSTNAME

# 3) Create a new user
adduser ubuntu
usermod -aG sudo ubuntu

# 4) Setup user ssh key
cat ~/.ssh/id_rsa.pub # on local computer and get ssh key

# on droplet
su - ubuntu 
mkdir ~/.ssh
chmod 700 ~/.ssh
vim ~/.ssh/authorized_keys # then paste the public key
chmod 600 ~/.ssh/authorized_keys


```
