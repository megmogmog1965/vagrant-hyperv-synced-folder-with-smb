# vagrant-hyperv-synced-folder-with-smb

This is for users using [Vagrant] with following situation.

* Windows 10 host OS
* CentOS6/7 guest OS.
* Hyper-V is enabled (maybe for [Docker])
* ``config.vm.synced_folder ..., type: "smb"``

CentOS6/7 Vagrant box cant mount smb synced folder without "mount_options" trick.

* [Synced Folders >> SMB >> Common Issues](https://www.vagrantup.com/docs/synced-folders/smb.html#common-issues)

Replace "USERNAME" and "PASSWORD" with your Windows login username and password.

```
Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.synced_folder ".", "/vagrant", type: "smb", smb_username: "USERNAME", smb_password: "PASSWORD", mount_options: ["username=USERNAME","password=PASSWORD"]
end
```

Then run vagrant with ``hyperv`` provider.

```
vagrant up --provider=hyperv
```

See also.

* https://github.com/hashicorp/vagrant/issues/8703
* https://github.com/hashicorp/vagrant/issues/8620
* https://github.com/hashicorp/vagrant/pull/9170


[Vagrant]:https://www.vagrantup.com/
[Docker]:https://www.docker.com/
