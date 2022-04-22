# Ansible postgres backup

First of all fill hosts.yaml file
```
web:
  hosts:
    server:
  vars:
    ansible_host: SERVER_IP # 192.192.192.191
    ansible_ssh_user: SUDO_USER # ansible
    ansible_port: SERVER_SSH_PORT # 22
    ansible_ssh_private_key_file: PATH_UNTIL_PRIVATE_KEY # if you have (/home/ansible/private_key.pem)
```

Also you need to fill vars section in playbook.yaml

```
db_name: DATABASE_NAME # ansible_db_name
postgres_db_port: POSTRESQL_PORT # default 5432
```

At the end run this command
```
ansible-playbook playbook.yaml -K
```
ansible will ask you to write sudo passpord.