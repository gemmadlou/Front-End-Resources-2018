# Ubuntu 16.04 Initial Setup

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

# Turn off password auth

PasswordAuthentication no # inside  /etc/ssh/sshd_config
PubkeyAuthentication yes
ChallengeResponseAuthentication no

sudo systemctl reload sshd

# Remove password for ubuntu

passwd -d ubuntu
echo 'ubuntu ALL=(ALL) NOPASSWD:ALL' | sudo EDITOR='tee -a' visudo

# 5) Setup basic firewall

sudo ufw app list

sudo ufw allow OpenSSH # IMPORTANT to allow us to log back in

sudo ufw enable

sudo ufw status


```


