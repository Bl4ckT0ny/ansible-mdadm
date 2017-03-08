Role Name
=========

An [Ansible] role to install and manage [mdadm] raid arrays.

Requirements
------------

- Available unpartitioned disk devices

Role Variables
--------------

```
---
# defaults file for ansible-mdadm
#
# Define Raid Arrays to manage
mdadm_arrays:
    # Define array name
  - name: 'md0'
    # Define disk devices to assign to array
    devices:
      - '/dev/sdb'
      - '/dev/sdc'
    # Define filesystem to partition array with
    filesystem: 'ext4'
    # Define the array raid level
    # 0|1|4|5|6|10
    level: '0'
    # Define mountpoint for array device
    mountpoint: '/mnt/md0'
    # Define if array should be present or absent
    state: 'present'
```

Dependencies
------------

None

Example Playbook
----------------

```
- hosts: all
  become: true
  vars:
  roles:
    - role: ansible-mdadm
  tasks:
```

License
-------

BSD

Author Information
------------------

Larry Smith Jr.
- [@mrlesmithjr]
- [EverythingShouldBeVirtual]
- mrlesmithjr [at] gmail.com

[@mrlesmithjr]: <https://www.twitter.com/mrlesmithjr>
[EverythingShouldBeVirtual]: <http://www.everythingshouldbevirtual.com>

[mdadm]: <https://linux.die.net/man/8/mdadm>
[Ansible]: <https://www.ansible.com>
