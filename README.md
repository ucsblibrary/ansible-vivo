# ansible_vivo
Ansible playbooks for Vivo

## Vagrant Server

Install external roles

    ansible-galaxy install -r required-roles.yml

Install seed provided by administrator in your root directory

    cp <source>/vault ~/.vault

Download a copy of vivo into the local files directory

    mkdir files
    cd files
    wget https://github.com/vivo-project/VIVO/releases/download/rel-1.8.1/vivo-rel-1.8.1.zip
    cd ..

Start the Vagrant server

    vagrant up

Once the server is up and running open your browser to [http://localhost:8080/vivo](http://localhost:8080.vivo)

Login with username and password below, substitute mydomain with the domain defined by vivo_domain

Username: `vivo_root@mydomain.edu`
Password: `rootPassword`
