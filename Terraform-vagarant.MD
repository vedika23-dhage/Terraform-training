# Create one folder in your machines
* Folder structure
  D drive -> Shared -> data
     
# Open VScode:
   Navigate to File -> open -> select your shared folder
  
# Run Vagrant command:
   * Click on folder data under shared.
   * Run command "vagrant init"
   * Note : You can find "Vagrantfile" which will be created automatically.
   * open "Vagrantfile" Delete all lines and update below code.

# Copy the below vagrant code to setup ubuntu virtual machine

```
# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.define "Terraformr" do |vm1|
    vm1.vm.hostname = "Terraform"
    vm1.vm.box = "bento/ubuntu-20.04"
    vm1.vm.network "private_network", ip: "192.168.33.10"
    vm1.vm.network "forwarded_port", guest: 8080, host: 9000, host_ip: "127.0.0.1", auto_correct: true
    vm1.vm.network "forwarded_port", guest: 80, host: 9001, host_ip: "127.0.0.1", auto_correct: true
    vm1.vm.provider "virtualbox" do |vb|
      vb.name = "Terraform"
      vb.gui = false
      vb.memory = "2024"
    end
  end
end
```

# Command to bring up the Virtual machines.
| Commands              | Purpose                       |
| --------------------- | ----------------------------  |
| vagrant up            | Brings up the virtual machine |
| vagrant ssh Terraform | ssh into the created machines |