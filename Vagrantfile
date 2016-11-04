# -*- mode: ruby -*-
# # vi: set ft=ruby :

Vagrant.configure("2") do |config|

 config.vm.synced_folder "shared", "/tmp/shared" 
  
	config.vm.define "challenge" do |challenge|
  
 		# Configuring Hostname
		challenge.vm.hostname= "JeevesMaster.qac.local"
  
		# Selecting the box to use
		challenge.vm.box = "chad-thompson/ubuntu-trusty64-gui"
	
		# Setting up the network options
		challenge.vm.network "public_network", :public_network=> "wlan0",ip:"192.168.1.113"
				
		# Calling the provision bash file
		challenge.vm.provision:shell,path:"bootstrap.sh"
		
		# Configuring vm provider options
		challenge.vm.provider "virtualbox" do |challengeVM|
  
			# Showing the vm GUI and setting its name
			challengeVM.gui = true
			challengeVM.name="ChallengeVM"
   
			# Setting the amount of RAM the VM has access to
			challengeVM.memory = "4096"
			challengeVM.cpus = "4"
		end
	end
end