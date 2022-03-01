### Some Basic Commands for Ansible



new role 
" ansible-galaxy init myrole"


ansible-playbook --connection=ssh --timeout=30 --extra-vars=ansible_user\=\'vagrant\' --limit="all" --inventory-file=inventory/dev/vagrant/hosts --become -vvv dbservers.yml
