Vagrant.configure("2") do |config|

    config.vm.define "server" do |s|
        s.vm.box = "ubuntu/xenial64"
        s.vm.network :private_network, ip:  "192.168.50.10"

        s.vm.provision "ansible" do |ansible|
            ansible.playbook = "playbook.yml"
            ansible.verbose = "-vvv"
        end
    end

    config.vm.define "client" do |c|
        c.vm.box = "ubuntu/xenial64"
        c.vm.network "private_network", ip: "192.168.50.11"
    end
end
