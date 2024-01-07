transmission
=========

This role deploy a [Transmission](https://transmissionbt.com/) server as a [Podman Quadlet](https://github.com/containers/quadlet) container.  

By default this role use the [Linux Server Transmission](https://github.com/linuxserver/docker-transmission) Docker Image.

Requirements
------------

* `podman` - version `4.7.2+`  

Role Variables
--------------

* `transmission_quadlet`: (`dict`) - Define the Container image and tag  
* `transmission_environment`: (`dict`) - Define the environment variables to be
  used by transmission. [Read more about
  envs](https://github.com/linuxserver/docker-transmission#docker-compose-recommended-click-here-for-more-info)  
* `transmission_volumes`: (`list`) - A list of directory paths to be mounted and
  created

Dependencies
------------

None

Example Playbook
----------------

* Deploy using default seetings:  

```yaml
---
- name: Deploy Transmission Quadlet
  hosts: all
  gather_facts: false
  roles:
    - role: transmission
```

_by default the deployment creates three volumens `config`, `downloads` and
`watch`, all directories are mounted from the host in the directory
`/srv/transmission`_  


Developing and Testing
----------------------

This role was developed using [ansible
molecule](https://ansible.readthedocs.io/projects/molecule/).
The use of molecule is optional but recommended.  
  
* Testing:  
Unit tests for checking code regression are available in the [`tests` directory](tests/).
use the `verify` or `test` commands, e.g:  

```bash
molecule test
```

while developing use `verify` instead:  

```bash
molecule create
molecule verify
```

License
-------

[GPL-2.0-or-later](https://spdx.org/licenses/GPL-2.0-or-later.html)

Author Information
------------------

@mrbrandao - Igor Brandão
