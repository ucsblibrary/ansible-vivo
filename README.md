# ansible_vivo

Ansible playbooks for Vivo

## Vagrant Server

Install external roles

    ansible-galaxy install -r required-roles.yml

Install seed provided by administrator in your root directory

    cp <source>/vault ~/.vault

Start the Vagrant server

    vagrant up

## Localhost Server

As above, except disploys to vagrant box using the ansible-playbook command.

Create a new `inventory/local/host` file containing:

    localhost ansible_user=vagrant ansible_port=2222 ansible_ssh_private_key_file=.vagrant/machines/default/virtualbox/private_key

Then run the playbook:

    ansible-playbook -i inventory/local playbook.yml

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

    ansible-playbook -i inventory/dev playbook.yml

## Begin Using Vivo

Once the server is up and running open your browser to http://vivo_domain.edu:8080/vivo
(or http://localhost:8080/vivo for Vagrant).

Login with username and password below, substitute vivo_root@mydomain.edu with the email
address defined by vivo_admin:

Username: `vivo_root@mydomain.edu`
Password: `rootPassword`

And change the administration password that a secure password.

# Theme Provisioning 

Provision the tulibraries/tuvivo_theme at `https://github.com/tulibraries/tuvivo_theme`.

- On Vagrant:

    ansible-playbook -i inventory/local build-theme.yml

- On the development server:

    ansible-playbook -i inventory/dev build-theme.yml

This will install or update the theme on the vivo server and restart tomcat. Wait 3-4 minutes
and refresh the browser.
