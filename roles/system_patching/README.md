Role Name: system_patching
=========

This role is for updating CentOS 6 and CentOS 7 servers. It will get a list of all running services, get the number of instances of Tomcat that are running, remove the exclude line in yum.conf, check for missing updates and report on how many are missing. It will compare the version of the running kernel with the version of the newest kernel under the /boot directory and report if they are different or the same.
If there was a Java update, or the newest installed kernel is different from the running kernel, the system will be rebooted.
Upon reboot it will check and make sure the services that were running before, are running then.
It will also check on running Tomcat instances and compare with the previous number and let you know if they differ.
Note that on CentOS 6 servers, it will NOT start any service that did not start, it will only do a comparison. This is a limitation of CentOS 6 service names.
Once patching completes, a notification email will be sent out to the address listed under the "notification_email" entry of the local fact file which lives on each system at /etc/ansible/facts.d/preferences.fact with the details of what happened during that patch cycle.
If no email address is found, the email will go to Aline Menezes so that can be corrected.
For a specific group of servers, a log file will be written for each server and copied to a central location for audit purposes.

Requirements
------------

N/A

Role Variables
--------------
This role uses local facts. Each server should have a local fact file located at /etc/ansible/facts.d/preferences.fact The service name and notification_email will be used for notifications.


----------------

This role is called by the system_patching.yml playbook.



Author Information
------------------

Aline Menezes
