# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  
  # Box Settings
  config.vm.box = "generic/ubuntu1604"

  # Provider Settings
  config.vm.provider "libvirt" do |vb|
    vb.memory = 1024
    vb.cpus = 1
    
  end

  # Network Settings
  # config.vm.network "forwarded_port", guest: 80, host: 8080
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"
  config.vm.network "private_network", ip: "192.168.33.10"

  # Folder Settings
  config.vm.synced_folder ".", "/var/www/html", :nfs => { :mount_options => ["dmode=777", "fmode=666"] }
  
  config.vm.provision "shell", path: "install_docker.sh"
end
