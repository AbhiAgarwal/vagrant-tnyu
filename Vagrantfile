# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
	config.vm.define :nodejsvm do |nodejs_config|
		nodejs_config.vm.box = "hashicorp/precise64"
		config.vm.network :private_network, ip: '10.0.33.34'
		config.vm.network "forwarded_port", guest: 80, host: 3000
		config.omnibus.chef_version = :latest
		nodejs_config.vm.provision :chef_solo do |chef|
			chef.cookbooks_path = "cookbooks"
			chef.add_recipe "build-essential"
			chef.add_recipe "git"
			chef.add_recipe "apt"
			chef.add_recipe "nodejs"
			chef.add_recipe "vim"
			chef.add_recipe "rvm"
		end
	end
end