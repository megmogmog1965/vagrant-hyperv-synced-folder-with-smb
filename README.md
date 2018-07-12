# vagrant-hyperv-synced-folder-with-smb

CentOS7 Vagrant box cant mount smb synced folder without "mount_options" trick.

* [Synced Folders >> SMB >> Common Issues](https://www.vagrantup.com/docs/synced-folders/smb.html#common-issues)

Replace "USERNAME" and "PASSWORD" with your SMB username and password.

```
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.synced_folder ".", "/vagrant", type: "smb", smb_username: "USERNAME", smb_password: "PASSWORD", mount_options: ["username=USERNAME","password=PASSWORD"]
end
```

Then run vagrant with hyperv.

```
vagrant up --provider=hyperv
```
