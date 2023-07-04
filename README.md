# Configuration Playbooks

This repository contains Ansible playbooks for configuring servers. These playbooks automate various tasks, such as server hardening, nginx installation and configuration, and docker deployment. 

## nginx.yml 
This playbook installs and configures the nginx server. The configuration is done using two templates: `nginx.conf.j2` and `site.j2`, which can be found in the `templates` directory.

## os+ssh_hardening.yml 
This playbook performs security hardening for the Linux operating system and SSH. The hardening tasks are performed using the `devsec.hardening` Ansible collection.

## dockers.yml 
This playbook installs and configures Docker. It also automatically deploys `watchtower` and `docker-telegram-notifier`. The telegram tokens for the latter can be provided in the `group_vars\docker.yml` file. The Docker installation is performed through the `install_docker` role, which can be found in the `roles\install_docker` directory.

## setup.yml 
This playbook performs the initial configuration of the VPS. Currently, it only performs user management. The tasks are performed through the `initialize` role, which can be found in the `roles\initialize` directory.

## Usage
To run the playbooks, you will need to have Ansible installed on your local machine. Once you have cloned this repository, navigate to its directory in the terminal and run the following command, replacing `<playbook_name>.yml` with the name of the playbook you want to run:
```
ansible-playbook <playbook_name>.yml
```
Note: You will also need to provide the target server information in the `hosts` file before running the playbook.
