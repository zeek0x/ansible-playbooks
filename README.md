# ansible-playbooks
my ansible template.

## 対象
### 環境
- Ubuntu 16.04

### ファイル
- /etc/source.list
- /etc/resolvconf/resolv.conf.d/base
- /etc/default/keyboard
- $HOME/.bashrc
- $HOME/.tmux.conf

### パッケージ
- gcc
- net-tools
- curl
- wget
- nmap
- direnv
- jq
- mysql-client
- sqlite3
- software-properties-common
- thunderbird
- tmux
- xsel
- virtualbox
- vagrant
- zip
- ansible
- atom
- libreoffice
- python3
- pip3
- ruby
- git
- nvm
- pyenv
- pyenv-virtualenv
- rbenv
- vivaldi
- slack
- dropbox
- docker
- circleci
- pip:docker-compose
- pip:pep8
- gem:bundler
- gem:rake

## 展開
### vagrant
#### 実行
```
$ cd ansbile-playbooks
$ vagrant up
$ ansible-playbooks -i development site.yml
```

### 実機
ssh ではパスワードログインを使用

#### ubuntu インストール
LiLi や unetbootin など

#### ssh 設定
- ネットワーク有効化

```
$ sudo apt-get update
$ sudo apt-get install python3
$ sudo -s /usr/bin/python3 /usr/bin/python
$ sudo passwd root
rootpass

$ sudo apt-get install openssh-server
$ sudo vi /etc/ssh/sshd_config
PermitRootLogin yes

$ sudo service ssh restart
```

#### 実機情報設定
production/hosts を書き換え
```
[host]
192.168.0.10

[servers:children]
host

[servers:vars]
ansible_ssh_user=user
ansible_ssh_pass=userpass
ansible_sudo_pass=rootpass
hoemdir=/home/ubuntu
```

#### 実行
```
$ cd ansbile-playbooks
$ ansible-playbooks -i production site.yml
```
