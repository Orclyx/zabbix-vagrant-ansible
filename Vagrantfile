Vagrant.configure("2") do |config|
  config.vm.define "server" do |server|
    server.vm.box = "bento/ubuntu-22.04"

    server.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
    server.vm.network "private_network", ip: "192.168.50.0"
  
    server.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "playbook.yml"
    end
  end

  config.vm.define "remote" do |remote|
    remote.vm.box = "bento/ubuntu-22.04"

    remote.vm.network "private_network", ip: "192.168.50.2"

    remote.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "remote-playbook.yml"
    end
  end

  config.vm.define "remote-secured" do |remote|
    remote.vm.box = "bento/ubuntu-22.04"

    remote.vm.network "private_network", ip: "192.168.50.3"

    remote.vm.provision "ansible" do |ansible|
      ansible.compatibility_mode = "2.0"
      ansible.playbook = "remote-secured-playbook.yml"
    end
  end
end
