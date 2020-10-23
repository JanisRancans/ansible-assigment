Vagrant.configure("2") do |config|

  config.vm.define "WordPressServer" do |server1|
    server1.vm.box = "ubuntu/bionic64"
    server1.vm.hostname = "wpserver"
    server1.vm.network "private_network", ip: "172.30.1.5"

    config.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.cpus = 2
    end
  end

  config.vm.define "MariaDBServer" do |server2|
    server2.vm.box = "ubuntu/bionic64"
    server2.vm.hostname = "dbserver"
    server2.vm.network "private_network", ip: "172.30.1.4"

    config.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.cpus = 2
    end
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisioning/playbook.yml"
  end
end
