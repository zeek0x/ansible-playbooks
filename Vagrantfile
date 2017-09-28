# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # https://atlas.hashicorp.com/bento/boxes/ubuntu-16.04/versions/2.3.0/providers/virtualbox.box
  config.vm.box = "ubuntu16.04"

  config.vm.network :private_network, ip: "192.168.33.10"

  # Install python2 for ubuntu16.04
  config.vm.provision :shell, inline: <<-SHELL
    if ! type python2.7 2>/dev/null 1>/dev/null; then
      apt -qq -y install python2.7
    fi
  SHELL
end
