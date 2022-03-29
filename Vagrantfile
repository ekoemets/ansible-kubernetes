Vagrant.configure("2") do |config|
    config.vm.box = "generic/centos8"

    config.vm.define "load_balancer" do |machine|
      machine.vm.hostname = "haproxy1.localdomain"
      machine.vm.network 'private_network',  ip: "192.168.56.9"
    end
    
    config.vm.define "master1" do |machine|
      machine.vm.hostname = "master1.localdomain"
      machine.vm.network 'private_network',  ip: "192.168.56.10"
    end

    config.vm.define "master2" do |machine|
      machine.vm.hostname = "master2.localdomain"
      machine.vm.network 'private_network',  ip: "192.168.56.11"
    end

    config.vm.define "node1" do |machine|
      machine.vm.hostname = "node1.localdomain"
      machine.vm.network 'private_network',  ip: "192.168.56.12"
    end

    config.vm.define "node2" do |machine|
      machine.vm.hostname = "node2.localdomain"
      machine.vm.network 'private_network',  ip: "192.168.56.13"
    end
end