# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box ="centos/7"


  config.vm.define "controller" , primary: true do |controller|
    controller.vm.network :private_network, ip: "192.168.61.10"

    controller.vm.provision :ansible_local do |ansible|
      ansible.playbook       = "playbook/install_docker.yaml"
      ansible.verbose        = "v"
      ansible.install        = true
      ansible.inventory_path = "hosts"
      ansible.compatibility_mode = "2.0"
    end
  end
end
