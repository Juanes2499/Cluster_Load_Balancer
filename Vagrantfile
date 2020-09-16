# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  config.vm.define "serverLoadBalancer" do |serverLoadBalancer|
    serverLoadBalancer.vm.box = 'bento/ubuntu-18.04'
    serverLoadBalancer.vm.network :private_network, ip: "192.168.102.2"
    serverLoadBalancer.vm.provision "shell", path:"StartUpServidor.sh"
    serverLoadBalancer.vm.hostname = "serverLoadBalancer"
    serverLoadBalancer.vm.network "forwarded_port", guest: 80, host: 3000
    serverLoadBalancer.vm.network "forwarded_port", guest: 8404, host: 8404
    serverLoadBalancer.vm.provider "virtualbox" do |v|
      v.memory = 1536
    end
  end

  config.vm.define :serverWeb1 do |serverWeb1|
    serverWeb1.vm.box = "bento/ubuntu-18.04"
    serverWeb1.vm.network :private_network, ip: "192.168.102.3"
    serverWeb1.vm.provision "shell", path:"StartUpServidor.sh"
    serverWeb1.vm.hostname = "serverWeb1"
    serverWeb1.vm.provider "virtualbox" do |v|
      v.memory = 1536
    end
  end

  config.vm.define :serverWeb2 do |serverWeb2|
    serverWeb2.vm.box = "bento/ubuntu-18.04"
    serverWeb2.vm.network :private_network, ip: "192.168.102.4"
    serverWeb2.vm.provision "shell", path:"StartUpServidor.sh"
    serverWeb2.vm.hostname = "serverWeb2"
    serverWeb2.vm.provider "virtualbox" do |v|
      v.memory = 1536
    end
  end

end