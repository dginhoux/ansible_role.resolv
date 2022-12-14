# ROLE dginhoux.resolv



## DESCRIPTION


This ansible role configure DNS resolver.<br />
It can be used to configure both legacy `/etc/resolv.conf` or `systemd-resolvd`.



## REQUIREMENTS

#### SUPPORTED PLATFORMS

This role require a supported platform.<br />
It will skip node with unsupported platform to avoid any compatibility problem.<br />
This behaviour can be bypassed by settings the following variable `asserts_bypass=True`.

| Platform | Versions |
|----------|----------|
| Debian | buster, bullseye |
| Fedora | 33, 34, 35, 36 |
| EL | 7, 8 |

#### ANSIBLE VERSION

Ansible >= 2.12

#### DEPENDENCIES

None.



## INSTALLATION

#### ANSIBLE GALAXY

```shell
ansible-galaxy install dginhoux.resolv
```
#### GIT

```shell
git clone https://github.com/dginhoux/ansible_role.resolv dginhoux.resolv
```


## USAGE

#### EXAMPLE PLAYBOOK

```yaml
- hosts: all
  roles:
    - name: start role dginhoux.resolv
      ansible.builtin.include_role:
        name: dginhoux.resolv
```


## VARIABLES

#### DEFAULT VARIABLES

Defaults variables defined in `defaults/main.yml` : 

```yaml
resolv_mode: legacy
# resolv_mode: resolved

resolv_nameservers:
  - 192.168.175.10
  - 192.168.175.11
  - 192.168.175.12
  - 192.168.175.13

resolv_search:
  - infra.ginhoux.net
  - ginhoux.net
```

#### DEFAULT OS SPECIFIC VARIABLES

Those variables files are located in `vars/*.yml` are used to handle OS differences.<br />
One of theses is loaded dynamically during role runtime using the `include_vars` module and set OS specifics variable's.

`NOT USED BY THIS ROLE`



## AUTHOR

Dany GINHOUX - https://github.com/dginhoux



## LICENSE

MIT
