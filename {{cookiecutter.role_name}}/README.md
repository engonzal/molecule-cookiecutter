# {{cookiecutter.role_name}}

Installs and configures 

[![Build Status](https://travis-ci.org/engonzal/ansible_role_{{cookiecutter.role_name}}.svg?branch=master)](https://travis-ci.org/engonzal/ansible_role_{{cookiecutter.role_name}})

## Requirements

Note that this role requires root.  Ensure become: yes is set at the top level of your playbook or invoke the role in your playbook like:

```yaml
- hosts: all
  roles:
    - role: engonzal.{{cookiecutter.role_name}}
      become: yes
```

## Role Variables

Available variable with examples are below:

```yaml
{{cookiecutter.role_name}}_servers:
  - time.cloudflare.com iburst prefer port 1514
{{cookiecutter.role_name}}_pools:
  - ntp.ubuntu.com        iburst maxsources 2
```

You can specify 

```yaml
{{cookiecutter.role_name}}_measurements_statistics_tracking: false
{{cookiecutter.role_name}}_disable_external_client: true
```

You can also enable 

## Example Playbook

### Simple Example (defaults)

```yaml
- hosts: servers
  roles:
      - { role: engonzal.{{cookiecutter.role_name}} }
```

### Advanced Example (custom server)

```yaml
- hosts: servers
  vars:
    {{cookiecutter.role_name}}_servers:
      # Custom time server with different port
      - time.example.com iburst prefer port 1514
      # Regular time server
      - time.cloudflare.com iburst prefer
  roles:
      - { role: engonzal.{{cookiecutter.role_name}} }
```

## License

BSD

## Author Information

This role was created in 2019 by Noe Gonzalez (<http://engonzal.com> and <https://buildahomelab.com>)
