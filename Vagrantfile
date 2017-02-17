# -*- mode: ruby -*-
# vi: set ft=ruby :

$script = <<SCRIPT
docker build -t evaluate/src /vagrant

kubectl apply -f /vagrant/rc.yaml
SCRIPT

Vagrant.configure("2") do |config|
    config.vm.box = "flixtech/kubernetes"

    config.vm.provider "virtualbox" do |vb|
        vb.memory = "2048"
        vb.cpus = 1
    end

    config.vm.provision "shell", inline: $script, privileged: false
end