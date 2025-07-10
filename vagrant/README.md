# Vagrant with VirtualBox User Guide

## Prerequisites
Before starting, make sure you have **VirtualBox** and **Vagrant** installed on your PC.

### Installing VirtualBox
To install VirtualBox, please refer to the official documentation : [VirtualBox Installation](https://www.virtualbox.org/wiki/Downloads)

### Installing Vagrant
To install Vagrant on Ubuntu/Debian, run the following commands :

```bash
wget -O - https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(grep -oP '(?<=UBUNTU_CODENAME=).*' /etc/os-release || lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install vagrant
```

You can verify the installation with :

```bash
vagrant --version
```

For more information, see the official documentation : [Vagrant Installation](https://developer.hashicorp.com/vagrant/downloads)

## Starting Virtual Machines
Once you are in the directory containing the `Vagrantfile`, run :


```bash
vagrant up
```

This command will :
- Download the Ubuntu Server image if it is not already cached.
- Create and configure the virtual machines defined in the `Vagrantfile`.

## Accessing a Virtual Machine
To connect to a VM via SSH, use :


```bash
vagrant ssh <vm_name>
```

Example for the master node :

```bash
vagrant ssh master
```

## Stopping Virtual Machines
To shut down all VMs without destroying them, use :

```bash
vagrant halt
```

To stop a single VM, specify its name :

```bash
vagrant halt <vm_name>
```

Example :
```bash
vagrant halt master
```

## Restarting Virtual Machines
To restart all VMs :

```bash
vagrant up
```

To restart a specific VM :

```bash
vagrant up <vm_name>
```

## Deleting Virtual Machines
To **completely remove** all VMs and their associated data, use :

```bash
vagrant destroy -f
```

To delete a single VM :

```bash
vagrant destroy -f <vm_name>
```

Example :
```bash
vagrant destroy -f master
```

## Listing Virtual Machines
To see the status of VMs managed by Vagrant, use :

```bash
vagrant status
```

To list running VMs in VirtualBox :

```bash
VBoxManage list runningvms
```


