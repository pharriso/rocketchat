Install RocketChat server
=========

Pre-reqs
------------

Fresh CentOS 7 server
FQDN for rocketserver in DNS

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

ansible-playbook -i <server name>, site.yml

Example

ansible-playbook -i 34.243.192.128, site.yml -u centos

Disable email validation for new users
------------

Log in with admin credentials. In the left-hand pane, press the 3 dots and then administration. Then **accounts** -> **registration** and untick **Accounts_Verify_Email_For_External_Accounts**
