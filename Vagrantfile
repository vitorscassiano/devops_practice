# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ubuntu/trusty64"

  config.vm.network "private_network", ip: "192.168.33.22"

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--memory", "1024"]
  end

  config.vm.provision "shell" do |shell|
    shell.inline = "sudo apt-get install ansible -y"
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "blog.yml"
    ansible.verbose = "vvv"
  end
end
