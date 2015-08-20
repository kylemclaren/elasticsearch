# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
	config.vm.define "elasticsearch-master" do |es|
		es.vm.hostname = "elasticsearch-master"
		es.vm.box = "hashicorp/precise64"
		es.vm.provision :ansible do |ansible|
			ansible.playbook = "test-master.yml"
		end
		es.vm.network "private_network", ip: "192.168.50.22"
	end
	config.vm.define "elasticsearch-data" do |es|
		es.vm.hostname = "elasticsearch-data"
		es.vm.box = "hashicorp/precise64"
		es.vm.provision :ansible do |ansible|
			ansible.playbook = "test-data.yml"
		end
		es.vm.network "private_network", ip: "192.168.50.23"
	end

end
