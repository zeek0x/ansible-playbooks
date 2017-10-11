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
- direnv
- jq
- nmap
- mysql-client
- sqlite3
- software-properties-common
- thunderbird
- tmux
- xsel
- virtualbox
- vagrant
- wget
- zip
- ansible
- atom
- libreoffice
- python
- pip
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
- root パスワード設定
```
$ sudo passwd root
rootpass
```

- ネットワーク有効化
- openssh-server インストール
```
$ sudo apt-get install openssh-server
```

- /etc/ssh/sshd_config で以下を書き換え
```
PermitRootLogin yes
```

- ssh リロード
```
sudo service ssh restart
```

#### 実機情報設定
production/hosts を書き換え
```
[host]
192.168.0.10

[servers:children]
host

[servers:vars]
ansible_ssh_user=root
ansible_ssh_pass=rootpass
hoemdir=/home/ubuntu
```

#### 実行
```
$ cd ansbile-playbooks
$ ansible-playbooks -i production site.yml
```
