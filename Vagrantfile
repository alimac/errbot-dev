# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"

    config.vm.provider "virtualbox" do |vb|
      vb.memory = "1024"
      vb.name = "errbot-dev"
    end

    config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get install python-pip -y
      sudo pip -q install err
      sudo pip -q install --upgrade six
      sudo pip -q install --upgrade sleekxmpp
      mkdir -p /vagrant/err-data
      mkdir -p /vagrant/err-plugins
    SHELL
end
