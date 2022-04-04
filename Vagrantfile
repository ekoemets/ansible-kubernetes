Vagrant.configure("2") do |config|
    config.vm.box = "generic/centos8"

    config.vm.define "load_balancer" do |machine|
      machine.vm.hostname = "haproxy1"
      machine.vm.network 'private_network',  ip: "192.168.56.5"
    end

    (1..2).each do |i|
      config.vm.define "master#{i}" do |machine|
        machine.vm.hostname = "master#{i}"
        machine.vm.network 'private_network',  ip: "192.168.56.1#{i}"
        machine.vm.provision :shell, inline: "sed 's/127\.0\.[01]\.1.*master.*/192\.168\.56\.1#{i} master#{i}/' -i /etc/hosts"
      end
    end

    (1..2).each do |i|
      config.vm.define "worker#{i}" do |machine|
        machine.vm.hostname = "worker#{i}"
        machine.vm.network 'private_network',  ip: "192.168.56.2#{i}"
        machine.vm.provision :shell, inline: "sed 's/127\.0\.[01]\.1.*worker.*/192\.168\.56\.2#{i} worker#{i}/' -i /etc/hosts"
      end
    end
end