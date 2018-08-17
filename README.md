endeca_mdex
=========
[![License](https://img.shields.io/badge/license-Apache-green.svg?style=flat)](https://raw.githubusercontent.com/lean-delivery/ansible-role-endeca-mdex/master/LICENSE)
[![Build Status](https://travis-ci.org/lean-delivery/ansible-role-endeca-mdex.svg?branch=master)](https://travis-ci.org/lean-delivery/ansible-role-endeca-mdex)
[![Build Status](https://gitlab.com/lean-delivery/ansible-role-endeca-mdex/badges/master/build.svg)](https://gitlab.com/lean-delivery/ansible-role-endeca-mdex)

## Summary
--------------

This role installs Oracle Endeca MDEX Engine on Linux platforms, which is the indexing and query engine that provides the backbone for all Endeca solutions.


Requirements
--------------

 - Minimal Version of the ansible for installation: 2.5
 - **Supported MDEX versions**:
   - 6.x.x
   - 11.x
   - _higher versions should be retested_
 - **Supported OS**:
   - CentOS
     - 6

For more information regarding support matrix please visit <https://support.oracle.com>


Role Variables
--------------

  - `endeca_user` - user for installing Endeca MDEX
  - `endeca_group` - group for endeca user

  - `transport` - artifact source transport  
     Available:
      - `web` - fetch artifact from custom web uri
      - `local` - local artifact

  - `transport_web` - URI for http/https artifact  e.g. "http://my-storage.example.com/V861206-01.zip"
  - `transport_local` - path for local artifact e.g. "/tmp/V861206-01.zip"

  - `download_path` - local folder for downloading artifacts  
    default: `/tmp/`

  - `mdex_version` - Endeca MDEX version

```
Set  MDEX version as it's defined in official Oracle Documentation
```

  - `base_root` - where MDEX should be installed  
    default: `/opt`

  - `mdex_port` - Endeca MDEX Engine user query port  
    default: `8000`


Example Playbook
----------------

### Installing Endeca MDEX 11.3.0 from local:
```yaml
- name: "Install MDEX 11.3.0 from local"
  hosts: all

  roles:
    - role: lean_delivery.endeca_mdex
      mdex_version: "11.3.0"
      transport: "local"
      transport_local: "/tmp/V861206-01.zip"
```

## License

Apache2

## Authors

team@lean-delivery.com
