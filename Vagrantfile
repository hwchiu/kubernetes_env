# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "bento/ubuntu-20.04"
  config.vm.box_version ='202112.19.0'
  config.vm.hostname = 'k8s-dev'
  config.vm.define vm_name = 'k8s'

  config.vm.provision "shell", privileged: false, inline: <<-SHELL
    set -e -x -u
    export DEBIAN_FRONTEND=noninteractive

    git clone https://github.com/hwchiu/kubernetes_env
    git clone --depth=1 https://github.com/Bash-it/bash-it.git ~/.bash_it
    bash ~/.bash_it/install.sh -s
  SHELL

  config.vm.network :private_network, ip: "10.22.33.44"
  config.vm.provider :virtualbox do |v|
      v.customize ["modifyvm", :id, "--cpus", 2]
      v.customize ["modifyvm", :id, "--memory", 4096]
      v.customize ['modifyvm', :id, '--nicpromisc1', 'allow-all']
  end
end
