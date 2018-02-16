nodes = [
   { :hostname => 'ubuntu-server.locale', :ip => '192.168.55.201', :ram => 1024, :os_vm => 'ubuntu/artful64', :playbook => 'kadNode'},
   { :hostname => 'centos-server.locale', :ip => '192.168.55.202', :ram => 1024, :os_vm => 'centos/7', :playbook => 'kadNode'}
]

Vagrant.configure("2") do |config|
  nodes.each do |node|
    config.vm.define node[:hostname] do |server|

      server.vm.box = node[:os_vm]
      server.ssh.insert_key = false
      #server.vm.synced_folder ".", "/vagrant", disabled: true
      server.vm.hostname = node[:hostname] + ".box"
      #
      # not working on ubuntu
      #server.vm.network :private_network, ip: node[:ip]

      server.vm.provider :virtualbox do |vb|
        vb.memory = node[:ram]
        vb.gui = false
        vb.linked_clone = true
        vb.name = node[:hostname]
      end

	  config.vm.provision "shell", inline: <<-SHELL
	  	  if [ -f /usr/bin/apt-get ]; 
			then
	      		apt-get update && apt-get install -y python
	      else
			echo "not ubuntu, python is installed"
			yum -y update
			# remove obsolete pyten version
			yum -y remove python
			
			cd /opt
			wget --no-check-certificate https://www.python.org/ftp/python/2.7.14/Python-2.7.14.tar.xz
			tar xf Python-2.7.14.tar.xz
			rm Python-2.7.14.tar.xz
			cd Python-2.7.14
			./configure --prefix=/usr/bin
			make && make install
		  fi
	   SHELL
      server.vm.provision "ansible" do |ansible|
        ansible.playbook = "ansible/" + node[:playbook] + ".yml"
      end

    end
  end
end