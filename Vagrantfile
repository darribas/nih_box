# -*- mode: ruby -*-
# # vi: set ft=ruby :
#

Vagrant.configure("2") do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"
    
    config.vm.provider :virutalbox do |vb|
        vb.customize [
            "modifyvm", :id,
            "--memory", "3072"
        ]
    end

    # Forward port 8080 to the host.
    config.vm.network "forwarded_port", guest:8888, host:8888

    # Provision the box
    config.vm.provision "shell", path: "bootstrap.sh"
    config.vm.provision "shell", privileged: false, path: "launchenv.sh", run: "always"
end

