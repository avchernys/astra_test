# ansible_local provisioner was introduced in 1.8
Vagrant.require_version ">= 1.8.0"

Vagrant.configure(2) do |config|
  config.vm.box = "generic/ubuntu2004"
  config.vm.provider "virtualbox"
  config.vm.network "public_network"
  config.vm.network "forwarded_port", guest: 3000, host: 3000
  config.vm.synced_folder ".", "/vagrant"

  config.vm.provision "ansible_local" do |ansible|
    ansible.playbook = "playbook.yml"
  end
end