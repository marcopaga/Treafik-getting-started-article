Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu/trusty64"
    config.ssh.insert_key = false

    config.vm.provider :virtualbox do |v|
        v.memory = 512
        v.cpus = 2
        v.customize ["modifyvm", :id, "--ioapic", "on"]
    end

    config.vm.define "server" do |s|
        s.vm.hostname = "server"
        s.vm.network :private_network, ip:  "172.16.2.10", auto_config: false, virtualbox__intnet: "isolated_network"
        s.vm.network "forwarded_port", guest: 8080, host: 8080

        s.vm.provision "ansible" do |ansible|
            ansible.playbook = "provision/playbook-server.yml"
            ansible.sudo = true
        end
    end

    config.vm.define "client" do |c|
        c.vm.hostname = "client"
        c.vm.network :private_network, ip:  "172.16.2.11", auto_config: false, virtualbox__intnet: "isolated_network"

        c.vm.provision "ansible" do |ansible|
            ansible.playbook = "provision/playbook-client.yml"
            ansible.sudo = true
        end
    end
end
