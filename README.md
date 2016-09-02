# Ansible-KVM-installer version 1.0

## Synopsis

Automate Installation process of KVM centos boxes with Ansible. You can specify the specs of VM during the installation process.
Please follow the guide in the next following lines to set up this playbook.

## Features to add
installing packages on the VM automatically after booting

Deploying mutiple VM at a time

Adding them to Monitoring services

## Code running example
```
ansible-playbook site.yml
```

This command will prompt you to enter the VM specs or if you prefer it to work with variable file, it will automate the installation accordingly. 



## Motivation
Aim to in the future create scaling VMs with Ansibles and futhure support all type of OS

## Installation
Note:
This require apache server set up and ansible set-up on the localhost.

1. Download the zip. Make a directory for the ansible playbooks in the location of your choice. Unpack the zip file in that directory

2. Next we will create a host list of servers we are working with in this directory. Run the following commmand


``cp /etc/ansible/hosts $your_directory_here``

This will copy the host file from ansible directory and we shall configure it to our own. Ansible playbook check the current directory first for cfg and host list and overwrite it before it look at the Ansible Directory for the default ones. You can ignore this step if you want to configure the main directory hosts file list and keep it all in 1 file for simplicity. In this case, please copy the unzipped folder to Ansible directory in /etc.

3.  Add the hosts that you want to configure in the host file.
```
[testbox]
$hostname ansible_hosts=$host_ip ansible_ssh_pass=$password ansible_user=$user
```
[Optional]
Here the username and password can be encrypted using ansible-vault. Please look into ansible documentation for this.

4. Please move the /files/ks/ to to /www/html/ks/

5. On the remote VM host, download the linux distro or use the Centos 6.5 iso that i provided below
Warning: If you are using Centos 6.5 version, the released iso will not work. You need to change the image according to the info i provided in the var file. You will need to scp transfer the iso file (inside file/iso/) to the remote host 

Centos 6.5 link: 
```
https://drive.google.com/open?id=0B1XWlzErQSfnb0NKYmljalk3cnc
```
6. Next we will change the var/main.yml. Please go to var/main.yml and make changes to the commented lines.

7. Next we will need to change the tasks/main.yml. Please naviagate to the file and make changes accordingly to the comments.

8. Go into /etc/ansible/ansible.conf
change the following:
```
[defaults]
host_key_checking = False
```
9. Get root access and we can run the ansible playbook using "ansible-playbook main.yml" in the tasks directory or you can include this role in your own playbook. You can rename this playbook and move it around to your convience.

##Things to do after installation:
Check out ansible-vault

Change /etc/hosts

Change defaults in /etc/ansible/CreateVM/roles/installation/tasks/main.yml

Change vars in /etc/ansible/CreateVM/vars/main.yml






