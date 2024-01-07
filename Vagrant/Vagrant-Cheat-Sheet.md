# Vagrant basic commands

## Starting

`vagrant init <BOX_NAME>`
Download a Vagrant box

`vagrant up`
Start the Vagrant VM

`vagrant ssh`
Connect to a VM via SSH

## Managing a Vagrant state

`vagrant up`
Start a Vagrant VM

`vagrant halt`
Stop a Vagrant VM

`vagrant resume`
Wake up a Vagrant VM

`vagrant reload`
Reload a Vagrant VM

`vagrant suspend`
Suspend a Vagrant VM

`vagrant destroy`
Stop and delete a Vagrant VM

## Vagrant VM status

`vagrant status`
Check a Vagrant VM state

`vagrant global-status`
Check ALL Vagrant VM status

## Provisioning

`vagrant provision`
Force provisioning

`vagrant provision --debug`
Use the debug flag to add more verbosity

`vagrant reload --provision`
Restart the VM and force provisioning

## Connecting to a VM

`vagrant ssh`
Connect to a Vagrant VM via SSH

`vagrant ssh <BOX_NAME>`
Connect to a specific Vagrant VM via SSH

## Managing boxes

`vagrant box list`
List all boxes installed

`vagrant box outdated`
Check of updates

`vagrant box add <BOX_NAME> <URL>`
Download a box

`vagrant box remove <BOX_NAME>`
Delete a box

# Vagrantfile examples

`config.vm.network "public_network"`
Add a bridged port

`config.vm.network "private_network", ip: "192.168.1.222"`
Add a bridged port with a static IP

```
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
    vb.cpus = 2
  end
```

Specify VM's memory and CPUs

```
config.vm.synced_folder "C:\\Users\\<YOUR_USERNAME>\\Desktop\\shared_files", "/home/vagrant/vagrant_data"
```

Share a folder from your host PC to the Vagrant VM

```
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2
  SHELL
```

Provisioning the VM
