Vagrant.configure("2") do |config|
    config.vm.box = "generic/centos8"
    
    config.vm.define "master" do |machine|
      machine.vm.hostname = "master.localdomain"
      machine.vm.network 'private_network',  ip: "192.168.56.10"
    end

    config.vm.define "node1" do |machine|
      machine.vm.hostname = "node1.localdomain"
      machine.vm.network 'private_network',  ip: "192.168.56.11"
    end


    config.vm.provision "ansible" do |ansible|    
        ansible.playbook = "cluster.yml"
        ansible.groups = {
          "k8s_control_plane" => ["master"],
          "k8s_node" => ["node1"]
        }
    end
end