# ansible-sudo-users
Ansible role for provisioning linux users adding them to sudo.

## Role Variables

This role requires the following variables:
- group: The linux user group
- users: List of users to be created

## Variable example:

```bash
group: "wheel"
users:
  - "user1"
  - "user2"
  - "user3"
```

## Requirements

There must be the SSH pub key of the user(s) in files folder, with the same name as the user(s) (i.e: user1.pub).

## Example Role Playbook

* `site.yml`

```ansible
- hosts: linux_servers
  roles:  
    - ansible-sudo-users
```

---
> **Ansible Role Structure Tree:**


```shell
.
├── ansible.cfg
├── hosts.ini
├── roles
│   └── ansible-sudo-users
│       ├── defaults
│       │   └── main.yml
│       ├── files
│       │   └── alexmbarbosa.pub
│       ├── handlers
│       │   └── main.yml
│       ├── LICENSE
│       ├── meta
│       │   └── main.yml
│       ├── README.md
│       ├── tasks
│       │   └── main.yml
│       ├── tests
│       │   ├── inventory
│       │   └── test.yml
│       └── vars
│           └── main.yml
└── site.yml
```

### Let's run!

```ansible
ansible-playbook site.yml
```

- Reference: https://docs.ansible.com/ansible/latest/playbook_guide/playbooks_reuse_roles.html

---
### License
GPL-3.0 License

### Author Information
Alex Mendes https://www.linkedin.com/in/mendesalex/
