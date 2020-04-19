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
