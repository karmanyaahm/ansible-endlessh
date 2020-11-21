# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|

  config.vm.box = "debian/buster64"

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "test.yml"
  end

  config.vm.network "forwarded_port", guest: 23, host: 2223, host_ip: "127.0.0.1"

end
