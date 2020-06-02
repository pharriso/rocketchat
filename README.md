Install RocketChat server
=========

Pre-reqs
------------

Fresh CentOS 7 server
FQDN for rocketserver in DNS

I tested this in AWS with Centos7 marketplace image and route53 dns.

Variables
------------

Set the following variable in site.yml

* **rocket_url:** rocket server fdqn

You will be prompted for the following:

* **admin_password:** admin password for rocketchat server
* **letsencrypt_email:** email address needed for letsencrypt

Running the playbook
------------

Run the playbook as follows. You mght need additional flags to specify ssh user etc

ansible-playbook -i rocket.example.com, site.yml -u centos


Configure RocketChat Students
=========

Pre-reqs
------------

Get a PAT token in RocketChat. Log in as the admin user, click on the "A" icon in the top left corner, "My Account" and then "Personal Access Token". Generate a new token and copy the user and token. 

Variables
------------

Set the following variable in configure_rocket.yml

* **rocket_url:** rocket server fdqn

You will be prompted for the following:

* **pat_user:** PAT user you generated in pre-req step
* **pat_token:** PAT token you generated in pre-req step
* **student_password:** Password to assign to student login. Worth setting this to the same password as the Ansible Labs

Running the playbook
------------

ansible-playbook configure_rocket.yml
