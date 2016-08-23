# Ansible-KVM-installer

## Synopsis

Automate Installation process of KVM centos boxes with Ansible. You can specify the specs of VM during the installation process.
Please follow the guide in the next following lines to set up this playbook.

## Code running example
```
ansible-playbook site.yml
```

This command will prompt you to enter the VM specs or if you prefer it to work with variable file, it will automate the installation accordingly. 



## Motivation
Aim to in the future create scaling VMs with Ansibles and futhure support all type of OS

## Installation

1. Download the zip. Make a directory for the ansible playbooks in the location of your choice. 
2. Next we will create a host list of servers we are working with in this directory. Run the following commmand


``cp /etc/ansible/hosts $your_directory_here``

This will copy the host file from ansible directory and we shall configure it to our own. Ansible playbook check the current directory first for cfg and host list and overright it before it look at the Ansible Directory for the default ones. You can ignore this step if you want to configure the main directory hosts file list and keep it all in 1 file for simplicity.

3.  

