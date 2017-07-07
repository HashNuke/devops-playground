# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  # config.ssh.private_key_path = File.expand_path "../data/ssh-keys/dummy-rsa", __FILE__

  shell_commands = [
    "cat /vagrant/data/ssh-keys/dummy-rsa.pub >> ~/.ssh/authorized_keys",
    "cat /vagrant/data/ssh-keys/dummy-rsa.pub | sudo tee -a /root/.ssh/authorized_keys",
    "sudo chmod -R 0700 /root/.ssh"
  ]


  config.vm.provision "shell",
    inline: shell_commands.join("; "),
    privileged: false


  config.vm.define "server1" do |named_vm|
    named_vm.vm.box = "ubuntu/xenial64"
    named_vm.vm.network "private_network", ip: "33.33.33.10"
  end


  config.vm.define "server2" do |named_vm|
    named_vm.vm.box = "ubuntu/xenial64"
    named_vm.vm.network "private_network", ip: "33.33.33.20"
  end


  config.vm.define "server3" do |named_vm|
    named_vm.vm.box = "ubuntu/xenial64"
    named_vm.vm.network "private_network", ip: "33.33.33.30"
  end


  config.vm.define "pg-playground" do |named_vm|
    named_vm.vm.box = "ubuntu/trusty64"
    named_vm.vm.network "private_network", ip: "33.33.33.40"
  end
end
