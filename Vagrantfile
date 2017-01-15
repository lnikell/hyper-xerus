# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure('2') do |config|
  config.vm.box      = 'nikel/xerus64'
  config.vm.hostname = 'hyper-box-xenial-xerus'

  config.vm.network :forwarded_port, guest: 3000, host: 3000
  config.vm.network :forwarded_port, guest: 35729, host: 35729

  config.vm.provision :shell, path: 'bootstrap.sh', keep_color: true
  config.vm.synced_folder "D:/Work/projects", "/home/vagrant/projects", type: "smb",smb_username: "alex", smb_password: "mystand"
  
  # Example configuration for shared folders for Internal Network
  #config.vm.synced_folder "F:/work/projects", "/home/vagrant/projects", type: "smb", smb_username: "user", smb_password: "password", smb_host: "192.168.137.1"
  #config.vm.synced_folder "F:/mystand-hyper-box", "/vagrant", type: "smb", smb_username: "user", smb_password: "password", smb_host: "192.168.137.1"
  
  config.vm.provider "hyperv" do |v|
    v.ip_address_timeout = 120
    v.cpus = 2
  end
end