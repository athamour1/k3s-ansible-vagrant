# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

	(1..3).each do |i|
		config.vm.define "worker#{i}" do |worker|
			worker.vm.box = "bento/ubuntu-22.04"
			worker.vm.network "private_network", ip: "192.168.0.11#{i}", virtualbox__intnet: true
			worker.vm.provider "virtualbox" do |workervm|
				workervm.memory = 4096
				workervm.cpus = 2
			end
		end
	end

	config.vm.define "master" do |master|
		master.vm.box = "bento/ubuntu-22.04"
		master.vm.network "private_network", ip: "192.168.0.110", virtualbox__intnet: true
		master.vm.provider "virtualbox" do |mastervm|
			mastervm.memory = 4096
			mastervm.cpus = 2
		end
	end

end
