# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.define "deployer" do |deployer|
    deployer.vm.box = "rockylinux/9"
    deployer.vm.hostname = "deployer"
    deployer.vm.network "private_network", ip: "192.168.56.5"

    deployer.vm.provision :ansible_local do |ansible_local|
      ansible_local.playbook = "playbooks/provision/deployer.yml"
    end
  end

  config.vm.define "alfa" do |alfa|
    alfa.vm.box = "rockylinux/9"
    alfa.vm.hostname = "alfa"
    alfa.vm.network "private_network", ip: "192.168.56.6"

    alfa.vm.provision :ansible_local do |ansible_local|
      ansible_local.playbook = "playbooks/provision/alfa.yml"
    end
  end

  config.vm.define "bravo" do |bravo|
    bravo.vm.box = "rockylinux/9"
    bravo.vm.hostname = "bravo"
    bravo.vm.network "private_network", ip: "192.168.56.7"
  end

  config.vm.define "charlie" do |charlie|
    charlie.vm.box = "rockylinux/9"
    charlie.vm.hostname = "charlie"
    charlie.vm.network "private_network", ip: "192.168.56.8"
  end

  config.vm.provider "virtualbox" do |v|
    v.memory = 2048 # default 8192
  end
end
