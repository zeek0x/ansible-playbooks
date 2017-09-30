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
```
$ cd ansbile-playbooks
$ vagrant up
$ ansible-playbooks -i development site.yml
```

### 実機
工事中
