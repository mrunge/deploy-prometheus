# deploy-prometheus
playbooks to deploy prometheus, collectd and collectd exporter in a OpenStack VM

# Instructions

Source your open.rc file, then inspect `group_vars/all.yml`.

You'd need to change the IP address (going to be a floating IP in OpenStack) with a free floating IP. Please also check, if there is a `m1.medium flavor`, a image to be taken as base. This can be either a RHEL based image or a CentOS image.
`os_security` names a security group, which should allow external access to ports 3000, 9090, 9100, and 9103. This is currently not set up via playbook. If you have a security role predefined in your OpenStack environment, name it here and it will be assigned to the used VM.

Run the playbook via

    ansible-playbook playbook.yml
