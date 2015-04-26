# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "debian74"

  config.vm.network "private_network", ip: "192.168.33.10"
  config.vm.synced_folder ".", "/vagrant", mount_options: ['dmode=777','fmode=777']

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/site.yml"
	ansible.inventory_path = "provisioning/development"
	ansible.limit = 'all'
	# ansible.verbose = 'vvvv'
  end
end
