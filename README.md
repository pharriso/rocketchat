Install RocketChat server
=========

Installs RocketChat on RHEL8 or CentOS 8. Used as part of Ansible workshops in UKI.

Requirements
------------

* A pre-deployed RHEL8 or CentOS8 server. You can provision your own instance or use one of the student environments from the Ansible Workshop.

Required Variables
------------

Edit the following variables in extra_vars.

| Name                      | Default value         |                                                                                  |
|---------------------------|-----------------------|----------------------------------------------------------------------------------|
| admin_password            | R0cket!               | **REQUIRED** Admin password.                                                     |


Optional Variables
------------

Edit the following variables in extra_vars.

| Name                      | Default value         |                                                                                  |
|---------------------------|-----------------------|----------------------------------------------------------------------------------|
| rocket_url                | inventory_hostname    | FQDN of RocketChat server                                                        |
| generate_letsencypt_certs | false                 | Whether to generate certificates. Not needed if using a workshop server.         |
| letsencrypt_emai          |                       | Email address for letsencrypt. Not needed if using a workshop server.            |
| redhat_workshop_server    | true                  | set this to false if you have provisioned your own server.                       |

Running the playbook
------------

Run the playbook as follows. You might need additional parameters to specify ssh user etc

example for a workshop server ...

```bash
ansible-playbook -i student1.ABCD.open.redhat.com, install_rocket.yml -u student1 -k -e @extra_vars
```

example for your own instance in ec2 ...

```bash
ansible-playbook -i rocket.mydomain.com, install_rocket.yml -u ec2-user --private-key=~/.ssh/id_rsa -e @extra_vars
```