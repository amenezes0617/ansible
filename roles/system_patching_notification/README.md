Role Name: system_patching_notification
=========

This role is used to send out pre-patching notification emails.
These emails will go out per server, on the morning of the patching cycle. They will go out to address found under the local fact notification_email.
Each server should have a local fact file /etc/ansible/facts.d/preferences.fact which will list that information.
If that is not found, the email will go to Aline Menezes so that can be corrected.

Role Variables
--------------
This role uses local facts. Each server should have a local fact file located at /etc/ansible/facts.d/preferences.fact The service name and notification_email will be used for notifications.
When used in Tower, it will use the fact caching feature to speed up variable search.

This role is called by the system_patching_notification.yml playbook.

Author Information
------------------

Aline Menezes
