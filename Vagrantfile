# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  # Box
  config.vm.box = "ubuntu/focal64"
  config.vm.box_version = "20220215.1.0"

  config.ssh.insert_key = false
  config.vm.synced_folder ".", "/vagrant", disabled: true

  # Provider & Specs
  config.vm.provider :virtualbox do |v|
    v.memory = 1024
    v.cpus = 1
  end

  config.vm.define "machine1" do |machine|
    machine.vm.hostname = "machine1"
    machine.vm.network :private_network, ip: "192.168.56.22"
  end
  config.vm.define "machine2" do |machine|
    machine.vm.hostname = "machine2"
    machine.vm.network :private_network, ip: "192.168.56.23"
  end
 


  config.vm.provision "ansible" do |ansible|
    ansible.compatibility_mode = "2.0"
    ansible.playbook = "dbservers.yml"
    ansible.inventory_path = "inventory/dev/vagrant/hosts"
    ansible.limit = "all"
    ansible.become = true
    ansible.verbose = "vvv"
    #ansible.config+file = 'ansible.cfg'
  end

end
