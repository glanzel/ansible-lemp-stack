# LEMP on Ubuntu 

This playbook will install a LEMP environment on an Ubuntu machine, as explained in the guide on
[Ansible Lemp Stack Setup ](https://www.kabelkopf.com/).
A virtualhost will be created with the options specified in the `vars/default.yml` variable file.

Ddditional it installs an ngnix-ui and git so you can deploy and administrate easier.

## Settings

- `mysql_root_password`: the password for the MySQL root account.
- `http_host`: your domain name.
- `http_conf`: the name of the configuration file that will be created within nginx.
- `http_port`: HTTP port, default is 80.
- `https_port`: HTTPS port, default is 443.
- `ssh_port`: SSH port, default is 22.


## Running this Playbook

Quick Steps:

### 1. Obtain the playbook
```shell
git clone https://github.com:glanzel/ansible-lemp-stack.git
cd ansible-lemp_stack
```

### 2. Customize Options

```shell
nano vars/default.yml
```

```yml
#vars/default.yml
---
mysql_root_password: "mysql_root_password"
http_host: "your_domain"
http_conf: "your_domain.conf"
http_port: "80"
```

### 3. Run the Playbook

```command
ansible-playbook -l [target] -i [inventory file] -u [remote user] playbook.yml
```

The Script is heavly inspired by 
[How to Use Ansible to Install and Set Up LEMP on Ubuntu 18.04](https://www.digitalocean.com/community/tutorials/how-to-use-ansible-to-install-and-set-up-lemp-on-ubuntu-18-04).
