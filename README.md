#A Role for adding and removing users in Mysql instances.
##Example playbook:
```
---
- name: mysql-user-operations
  hosts: master
  become: yes
  roles:
    - {role: ansible-mysql-operations}
  vars:
    adding_name: 'jackie.chan'
    adding_password: '1234'
    adding_host: '%'
    adding_priv: '*.*:SELECT'
    removing_name: 'jackie.chan'
```
##You need to create a playbook like the above example to make changes.
##The role supports multiple actions in instances such as adding and removing more than one user at a time.
###The command for adding user:
> ansible-playbook -i inventory test.yml --tags="add"
###To remove it, define the user name to removing_name:
> ansible-playbook -i inventory test.yml --tags="remove"
###No need tags anymore if you like to add and remove users
> ansible-playbook -i inventory test.yml

