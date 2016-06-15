# ansible_vivo
Ansible playbooks for Vivo

## Vagrant Server

Install external roles

    ansible-galaxy install -r required-roles.yml

Install seed provided by administrator in your root directory

    cp <source>/vault ~/.vault

Start the Vagrant server

    vagrant up

Once the server is up and running open your browser to [http://localhost:8080/vivo](http://localhost:8080.vivo)

Login with username and password below, substitute mydomain with the domain defined by vivo_domain

Username: `vivo_root@mydomain.edu`
Password: `rootPassword`

## Target Server

If not already done, install external roles

    ansible-galaxy install -r required-roles.yml

Install seed provided by administrator in your root directory

    cp <source>/vault ~/.vault

Upload your public ssh key to the server, if necessary.

    cat $HOME/.ssh/id_rsa.pub | ssh <username>@<vivo_domain.edu> 'cat >> .ssh/authorized_keys'

Modify inventory/dev/hosts file as appropriate:


    vivo_domain.edu ansible_user=<username> ansible_ssh_private_key_file=$HOME/.ssh/id_rsa

Run the ansible playbook to deploy the new site.

    ansible-playbook -i inventory/dev/hosts playbook.yml --vault-password-file=~/.vault --ask-sudo-pass

Once the server is up and running open your browser to http://vivo_domain.edu:8080/vivo

Login with username and password below, substitute mydomain with the domain defined by vivo_domain

Username: `vivo_root@mydomain.edu`
Pansible-playbook -i inventory/dev/hosts playbook.yml --vault-password-file=~/.vault --ask-sudo-password: `rootPassword`
