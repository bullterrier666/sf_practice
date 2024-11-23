Vagrant.configure("2") do |config|

	config.vm.box = "geerlingguy/ubuntu1804"
	config.vm.network "public_network", ip: "192.168.0.15"

	config.vm.provider "virtualbox" do |vb|
		vb.memory = 4096
		vb.cpus = 3
	end

    config.vm.provision "file", source: "empty_file.txt", destination: "/home/vagrant/empty_file.txt"
    config.vm.provision "shell", inline: <<-SHELL
      apt-get update
      apt-get install mc -y
      apt-get install python3 -y
      apt-get install python3-pip -y
      apt-get install python3-psycopg2 -y
      pip3 install django
    SHELL
end