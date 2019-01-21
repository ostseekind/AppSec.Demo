# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

	config.vm.box = "ubuntu/trusty64"
	config.vm.hostname = "appsec-demo"
	# config.vm.box_url = 
	# config.box_version = 
	
	# config.vm.network "forwarded_port", guest: 80, host: 8080
	# config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

	config.vm.network "private_network", ip: "10.20.30.60"
	# config.vm.network "public_network"

	config.vm.provider "virtualbox" do |v|
		v.name = "appsec-demo"
		v.memory = 512 #4096
		v.cpus = 1 #4
	end
	# Enable provisioning with a shell script. Additional provisioners such as
	# Puppet, Chef, Ansible, Salt, and Docker are also available. Please see the
	# documentation for more information about their specific syntax and use.
	config.vm.provision "shell", path: "install/ansible.sh"
	config.vm.provision "ansible_local" do |ansible|
		ansible.playbook = "./install/main.yml"
	end
	#   apt-get update
	#   apt-get install -y apache2
	#SHELL
end
