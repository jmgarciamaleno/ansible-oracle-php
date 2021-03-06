# Ansible Oracle connection from PHP role

Simple and specific Ansible role to configure access to an Oracle 11.2 access from PHP 5.6 in Ubuntu 14.04.

This role is based on the instructions from [The ************* way to get Oracle database connections in PHP5 over Ubuntu](https://github.com/tassoevan/pdo-oci-extension), with a couple changes.

The PHP extensions ```oci8``` and ```pdo_oci``` will be enabled in the PHP configuration.

Oracle's sqlplus client will be installed. Usage: ```sqlplus <USER>/<PASS>@<HOST>/<SERVICE>```

## Prerequisites

- Ubuntu 14.04
- PHP 5.6 installed from the [ppa:ondrej/php](https://launchpad.net/~ondrej/+archive/ubuntu/php) repository

## Usage

1. Edit the ```hosts``` file and fill it with your hosts data.

2. Add the hosts to provision to the ```- hosts:``` line in ```oracle-php.yml```.  
   The given hosts may be a single host, a group or a list of comma-separated hosts/groups.
   E.g:
     - ```- hosts: [project1-group]```
     - ```- hosts: project1-dev```

5. Run:
    * ```ansible-playbook -i hosts oracle-php.yml --ask-pass --become --ask-become-pass```  
    or
    * ```ansible-playbook -i hosts oracle-php.yml -k -b -K```

## License

This code is distributed under the MIT license: [LICENSE](LICENSE).
