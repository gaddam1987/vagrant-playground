# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box ="centos/7"

  config.vm.define "controller" , primary: true do |controller|
    controller.vm.network :private_network, ip: "192.168.61.10"

    controller.vm.provision :ansible_local do |ansible|
      ansible.playbook       = "playbook/ping.yaml"
      ansible.verbose        = true
      ansible.install        = true
      ansible.limit          = "controller" # or only "nodes" group, etc.
      ansible.inventory_path = "hosts"
    end
  end
end

