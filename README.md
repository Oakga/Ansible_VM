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

1. Download the zip. Make a directory for the ansible playbooks in the location of your choice. Unpack the zip file in that directory

2. Next we will create a host list of servers we are working with in this directory. Run the following commmand


``cp /etc/ansible/hosts $your_directory_here``

This will copy the host file from ansible directory and we shall configure it to our own. Ansible playbook check the current directory first for cfg and host list and overright it before it look at the Ansible Directory for the default ones. You can ignore this step if you want to configure the main directory hosts file list and keep it all in 1 file for simplicity.

3.  Add the hosts that you want to configure. 
```
[sandbox]
$hostname ansible_hosts=$host_ip ansible_ssh_pass=$password ansible_user=$user
```

Here the username and password can be encrypted using ansible-vault. Please look into ansible documentation for this.

4. next we will change the var files. Please go to var/main.yml and change the remote_user ssh pass in there. 


5. Then you can run this role in your playbook with "ansible-playbook $playbook_name"



