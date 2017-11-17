# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box ="centos/7"
  config.vm.network "forwarded_port", guest: 8080, host: 8080
  config.vm.network "forwarded_port", guest: 29418, host: 29418

  config.vm.define "controller" , primary: true do |controller|
    controller.vm.provision :ansible_local do |ansible|
      ansible.playbook       = "playbook/main.yaml"
      ansible.verbose        = "v"
      ansible.install        = true
      ansible.inventory_path = "hosts"
      ansible.compatibility_mode = "2.0"
    end
  end
end
