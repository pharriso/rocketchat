Install RocketChat server
=========

Pre-reqs
------------

RHEL8 server. You can provision your own or use an ansible workshop server
FQDN for rocketserver in DNS

Variables
------------

Set the following variable in extra_vars

* **rocket_url:** rocket server public fqdn

* **admin_password:** if you want it to automatically configure the admin user

* **generate_letsencypt_certs:** set to true if you have provisioned your own instance. Not needed if using a workshop server

* **letsencrypt_email:** needed if you have provisioned your own instance. Not needed if using a workshop server

* **redhat_workshop_server:** set this to false if you have provisioned your own rhel8 server


Running the playbook
------------


Change any occurences of 'ABCD' to the actual provisioned details when using RHPDS.


Run the playbook as follows. You might need additional flags to specify ssh user etc

example for a workshop environment ...

ansible-playbook -i student1.ABCD.open.redhat.com, install_rocket.yml -u student1 -k -e @extra_vars

example for your own instance in ec2 ...

ansible-playbook -i rocket.mydomain.com, install_rocket.yml -u ec2-user --private-key=~/.ssh/id_rsa -e @extra_vars


Configure RocketChat Students
=========

Pre-reqs
------------

Get a PAT token in RocketChat. Log in as the admin user, click on the "A" icon in the top left corner, "My Account" and then "Personal Access Token". Set authentication to ignore two factor authentication and call it 'workshop'. Generate a new token and copy the user and token. 

Variables
------------

Set the following variable in extra_vars

* **rocket_url:** rocket server public fdqn
* **students:** number of students to configure


You will be prompted for the following:

* **pat_user:** PAT user you generated in pre-req step
* **pat_token:** PAT token you generated in pre-req step
* **student_password:** Password to assign to student login. Worth setting this to the same password as the Ansible Labs

Running the playbook
------------

ansible-playbook configure_rocket.yml -e @extra_vars

Setting friendly names in RocketChat
------------

This is completely optional - if you want to set the display for users to real names then as the admin user, go to "Options", "Administration", "Layout", "User Interface" and select "Use Real Name".


