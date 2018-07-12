# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # centos7
  config.vm.box = "centos/7"
  config.vm.synced_folder ".", "/vagrant", type: "smb", smb_username: "USERNAME", smb_password: "PASSWORD", mount_options: ["username=USERNAME","password=PASSWORD"]

  # ubuntu-16.04
  #config.vm.box = "bento/ubuntu-16.04"
  #config.vm.synced_folder ".", "/vagrant", type: "smb", smb_username: "USERNAME", smb_password: "PASSWORD"

end
