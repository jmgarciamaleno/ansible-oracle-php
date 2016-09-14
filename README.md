# Ansible Oracle connection from PHP role

Simple Ansible role to configure Oracle 11.2 access from PHP 5.6 in Ubuntu 14.04.

This role is based on the instructions from [The ************* way to get Oracle database connections in PHP5 over Ubuntu](https://github.com/tassoevan/pdo-oci-extension), with a couple changes.

The PHP extensions ```oci8``` and ```pdo_oci``` will be enabled in the PHP-FPM configuration.

Oracle's sqlplus client is also installed. Connection string: ```sqlplus <USER>/<PASS>@<HOST>/<SERVICE>```

## Prerequisites

The remote host must have PHP 5.6 installed from the [ppa:ondrej/php](https://launchpad.net/~ondrej/+archive/ubuntu/php) official repository.

## Usage

1. Edit the ```hosts``` file and fill it with your hosts data.

2. Add the hosts to provision to the ```- hosts:``` line in ```oracle-php.yml```.  
   The given hosts may be a single host, a group or a list of comma-separated hosts/groups.
   E.g:
     - ```- hosts: [project1-group]```
     - ```- hosts: project1-dev```

3. Run: ```ansible-playbook -i hosts oracle-php.yml --ask-pass --ask-become-pass```

## Vagrant

A Vagrantfile is provided to create a local VM (Vagrant and Virtual Box required) with ip ```192.168.33.101```, to test this playbook against it.

An ```admin``` user is added (password requested) when the machine is created. You can use the standard ```vagrant``` user too.

Usage: ```vagrant up```

## License

This code is distributed under the MIT license: [LICENSE](LICENSE).
