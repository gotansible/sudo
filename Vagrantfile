# -*- mode: ruby -*-
# vi: set ft=ruby :

system("
    if [ #{ARGV[0]} = 'up' ]; then
        echo 'You are doing vagrant up and can execute your script'
        ansible-galaxy install -r requirements.yml --force
    fi
")

VAGRANT_VERSION = 2
Vagrant.configure(VAGRANT_VERSION) do |config|
	config.vm.define "sudo" do |server|
		server.vm.box = "hashicorp/precise64"
		server.vm.hostname = "sudo"
		server.vm.provision :ansible do |ansible|
			ansible.playbook = "test.yml"
		end
	end
end
