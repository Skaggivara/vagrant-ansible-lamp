quick-dev-env
=============

Automatically configures a LAMP stack, and supported CMS's using Vagrant and Ansible

**Currently supported CMS's:**

* Wordpress
* Perch CMS

## Requirements

* VirtualBox [https://www.virtualbox.org/wiki/Downloads](https://www.virtualbox.org/wiki/Downloads)
* Vagrant [http://www.vagrantup.com/](http://www.vagrantup.com/)
* Ansible [http://docs.ansible.com/intro_installation.html](http://docs.ansible.com/intro_installation.html). The easiest way is with homebrew: `brew install ansible`


## Getting Started

1. Fork or clone this project and enter the directory in a terminal
1. Edit `ansible/development.yml` to suit
1. Change settings in `/ansible/group_vars/vagrant` to suit
1. Run vagrant up to provision your VM, and run the server
1. View `http://[project_name].192.168.111.100.xip.io/`

The first time you run `vagrant up` can take quite a while (~15 mins)