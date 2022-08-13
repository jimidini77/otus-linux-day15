# -*- mode: ruby -*-
# vim: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "centos/7"

  config.vm.provision "ansible" do |ansible|
    #ansible.verbose = "vvv"
    ansible.playbook = "nginx-role.yml"
    ansible.become = "true"
  end

  config.vm.provider "virtualbox" do |v|
	  v.memory = 256
  end

  config.vm.define "nginx" do |nginx|
    nginx.vm.network "private_network", ip: "192.168.56.10", virtualbox__intnet: "dns"
    nginx.vm.hostname = "nginx"
  end

end
