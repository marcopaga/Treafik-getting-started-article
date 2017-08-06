Vagrant.configure("2") do |config|

    config.vm.box = "ubuntu/trusty64"
    config.ssh.insert_key = false

    config.vm.provider :virtualbox do |v|
        v.memory = 512
        v.cpus = 2
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        v.customize ["modifyvm", :id, "--ioapic", "on"]
    end

    config.vm.define "server" do |s|
        s.vm.hostname = "server"
        s.vm.network :private_network, ip:  "172.16.2.10"

        s.vm.provision "ansible" do |ansible|
            ansible.playbook = "provision/playbook.yml"
            ansible.verbose = "-vvv"
            ansible.sudo = true
        end
    end

    config.vm.define "client" do |c|
        c.vm.hostname = "client"
        c.vm.network :private_network, ip:  "172.16.2.11"
    end
end
