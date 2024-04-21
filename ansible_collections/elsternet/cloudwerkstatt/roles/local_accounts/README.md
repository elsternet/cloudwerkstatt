# roles/local_accounts/README.md
---
name: local_accounts
description: >
  This role configures local user accounts with variables provided from a dictionary in vars/main.yml

vars/main.yml:
  # user dictionary to define user account details to be set
  name: user account name
  shell: user account preferred shell - default '/bin/bash'
  userid: the users desired userid
  expires: the accounts expiry date in epoch time - set "-1" for disabled, i.e. does not expire
  groups: list the groups the account should be member of
  home_dir: specify the path to the user's home directory

files: 
  # storage for public keys to be added to authorized keys for the generated users. Keyfiles need to follow the following naming, using the user account name as used in vars/main.yml: 
  "<user account name>.key.pub"


# Dependencies
- none

# Example Playbook
- hosts: all 
  roles:
    - role: local_accounts
      vars:
        users:
          - name: 'local_log'
            shell: '/bin/sh'
            userid: '38000088'
            expires: 1734044399
            groups: ''
            home_dir: '/home/local_log'
