[![CI](https://github.com/de-it-krachten/ansible-role-sysctl/workflows/CI/badge.svg?event=push)](https://github.com/de-it-krachten/ansible-role-sysctl/actions?query=workflow%3ACI)


# ansible-role-sysctl

Installs/configures/manages sysctl



## Dependencies

#### Roles
None

#### Collections
- ansible.posix

## Platforms

Supported platforms

- Red Hat Enterprise Linux 8<sup>1</sup>
- Red Hat Enterprise Linux 9<sup>1</sup>
- Red Hat Enterprise Linux 10<sup>1</sup>
- RockyLinux 8
- RockyLinux 9
- RockyLinux 10
- OracleLinux 8
- OracleLinux 9
- OracleLinux 10
- AlmaLinux 8
- AlmaLinux 9
- AlmaLinux 10
- Debian 11 (Bullseye)
- Debian 12 (Bookworm)
- Debian 13 (Trixie)
- Ubuntu 20.04 LTS
- Ubuntu 22.04 LTS
- Ubuntu 24.04 LTS

Note:
<sup>1</sup> : no automated testing is performed on these platforms


## Role Variables
### defaults/main.yml
<pre><code>
# dict of sysctl settings
sysctl_settings: {}
</pre></code>




## Example Playbook
### molecule/default/converge.yml
<pre><code>
- name: sample playbook for role 'sysctl'
  hosts: all
  become: 'yes'
  vars:
    molecule_driver: '{{ lookup(''env'', ''MOLECULE_DRIVER_NAME'') }}'
    sysctl_settings:
      net.ipv4.conf.default.rp_filter: '1'
      net.ipv4.ip_forward: '1'
      net.ipv4.ip_nonlocal_bind: '1'
  tasks:
    - name: Include role 'sysctl'
      ansible.builtin.include_role:
        name: sysctl
</pre></code>
