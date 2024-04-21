# roles/ssh_config/README.md
---
This role configures the ssh service to set the following options:

          - PermitRootLogin no
          - PasswordAuthentication yes
          - PermitEmptyPasswords no
  It also restarts the ssh service should changes have been made, so changes will be applied. 

# Dependencies
- none

# Example Playbook
        - hosts: all 
          roles:
            - role: ssh_config