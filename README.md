# VPS/VDS Auto-Configuration with Ansible

Automated VPS/VDS server provisioning and security hardening using Ansible. This repository contains battle-tested playbooks to transform a fresh Linux server into a secure, production-ready system in minutes.

## Features

- **SSH Security Hardening** - Secure configuration, key-based authentication, port customization
- **Firewall Setup** - iptables/nftables configuration with sensible defaults
- **Fail2Ban Protection** - Automatic blocking of brute-force attacks
- **User Management** - Secure user creation with sudo privileges
- **Package Installation** - Essential packages and tools

## Quick Start

### Prerequisites
- Ansible core 2.16.3+ installed on your local machine
- SSH access to your VPS/VDS server && installed sshpass package 
- Python 3.x on the target server

### Usage
```bash
git clone https://github.com/dimasikks/configuration_VPS.git cvps
cd cpvs
ansible-playbook playbooks/configuration.yml
```
### Project structure
```bash
cvps/
├── ansible.cfg                                # default ansible parameters
├── inventory
│   └── groups
│       └── all.yml                            # host inventory (change)
├── playbooks
│   └── configuration.yml                      # main playbook
└── roles
    └── configuration
        ├── defaults
        │   └── main.yml                       # default vars (change)
        ├── handlers
        │   └── main.yml                       # handlers
        ├── tasks                              # main tasks for installation, configuration and preparation VPS/VDS server, do not change
        │   ├── base.yml
        │   ├── main.yml
        │   ├── secure.yml
        │   └── ssh_keys.yml
        ├── templates                          # templates of installation components, change the template based on the requirements (change)
        │   ├── iptables.primary
        │   ├── jail.local.primary
        │   └── sshd_config.primary
        └── vars                               # main vars  (change)
            ├── main.yml                       # include configurations
            ├── base.yml                       # base configuration
            └── secure.yml                     # secure configuration
```
