'''
# generate ssh key
ssh-kengen -t rsa -C "Zhengkai.z.wang@gmail.com" -f ~/.ssh/id_rsa_sth
ssh-agent zsh
ssh-add ~/.ssh/id_rsa_sth
scp ~/.ssh/id_rsa_sth.pub target_ip_address:~/.ssh

# add in ~/.ssh/config
Host ip_name
  HostName ip_address
  # ssh port default 22
  Port 22
  IdentityFile ~/.ssh/id_rsa_sth

# host shell
ssh target_ip_address
cat ~/.ssh/id_rsa_sth.pub >> authorized_keys

# git config
# --system /etc/gitconfig --global ~/.gitconfig --local ./.git/config
git config --global user.name "ZK"
git config --global user.email "Zhengkai.Z.Wang@gmail.com"
git config --global core.editor emacs
