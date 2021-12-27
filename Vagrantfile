Vagrant.configure("2") do |config|

  config.vm.box = "ubuntu/bionic64"
  config.ssh.forward_agent = true
  config.vm.provider "virtualbox" do |vb|
    vb.memory = 1024
  end

  config.vm.define "wordpress" do |m|
	   m.vm.network "public_network", ip: "192.168.1.62"
     m.vm.provision "shell", 
      inline: "cat /vagrant/config/id_bionic.pub >> .ssh/authorized_keys"
  end

  config.vm.define "mysql" do |m|
    m.vm.network "public_network", ip: "192.168.1.63"
    m.vm.provision "shell", 
     inline: "cat /vagrant/config/id_bionic.pub >> .ssh/authorized_keys"
  end

end
