# ansible_vivo
Ansible playbooks for Vivo

## Vagrant Server

Install external roles

    ansible-galaxy install -r required-roles.yml

Install seed provided by administrator in your root directory

    cp <source>/vault ~/.vault

Start the Vagrant server

    vagrant up

Log onto ther server

    vagrant ssh
