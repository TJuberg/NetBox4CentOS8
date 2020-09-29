# NetBox4CentOS8

This playbook will install Netbox on a clean CentOS 8 system, all the way through. The only work needed is to input a few values in `vars/config.yml`.

Why make this? Official install documentation lacks proper procedure for CentOS 8. It's easy to figure out, but having a playbook makes the entire setup process extremely quick and easy.

You can easily make a few small adjustments for CentOS 7 if desired.

## How to

### 1. Fill in the `var/config.yml` 

`auth` specifies the PostgreSQL username and password.

`config` specifies your Netbox site's ip address and domain.

`app` specifies the actual Netbox app/site's admin user credentials.

`ssl` specifies the self-signed cert information. These are option and can be left blank.

### 2. Run the playbook

Yep, that easy.

## NOTES:
Designed for a fresh install, and should only need to be ran once. 

Some conditionals are added for increased idempotency, if you stop or encounter errors, but running on a system with previous install is unlikely to work.

Running `config.sh` takes some time. Don't stop the playbook during this task.

The playbook WILL hang if you're trying to create a user for the NetBox app that already exists.

I assume a registered DNS name is used. Modify the `httpdconf.j2` file if needed.
  
## Further Reading:

Offical Netbox Docs: https://netbox.readthedocs.io

Netbox Community Github: https://github.com/netbox-community

Netbox Ansible Modules Docs: https://netbox-ansible-collection.readthedocs.io/en/latest/

## Coming Soon
Soon I'll share my playbooks and demonstrate how we automatically populate server-data and rack location.
