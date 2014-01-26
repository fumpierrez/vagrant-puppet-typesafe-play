
Vagrant.configure("2") do |config|
	config.vm.box = "lucid32"

	# Enable the Puppet provisioner
 	config.vm.provision :puppet, :module_path => "modules"

	config.vm.provider :virtualbox do |vb|
		vb.name = "fraviroel-local"
		vb.memory = 768
		vb.customize [ "modifyvm", :id, "--memory", "768" ]
	end

	# Forward guest port 80 to host port 4567
	config.vm.network "forwarded_port", guest: 80, host: 4567
	config.vm.network "forwarded_port", guest: 9000, host: 9000

	 config.vm.synced_folder "/fraviroel/", "/fraviroel"
end

