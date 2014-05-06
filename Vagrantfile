# -*- mode: ruby -*-
# vi: set ft=ruby :

#Note: using vbguest plugin to manage guest addition upgrades
#https://github.com/dotless-de/vagrant-vbguest

Vagrant.configure("2") do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  # Make this VM reachable on the host network as well, so that other
  # VM's running other browsers can access our dev server.
  config.vm.network :private_network, ip: "192.168.111.100"

  # Make it so that network access from the vagrant guest is able to
  # use SSH private keys that are present on the host without copying
  # them into the VM.
  config.ssh.forward_agent = true

  config.vm.network :forwarded_port, guest: 80, host: 8080

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "ansible/development.yml"
    ansible.groups = {
      "vagrant" => ["default"]
    }
  end
end