Ansible Role Flatpak
=========

[![Molecule Test](https://github.com/diademiemi/ansible_role_flatpak/actions/workflows/molecule.yml/badge.svg)](https://github.com/diademiemi/ansible_role_flatpak/actions/workflows/molecule.yml)

This is an Ansible role to install and configure Flatpak and optionally add Flathub and install/uninstall packages.

Requirements
------------
These platforms are supported:
- Ubuntu 20.04  
- Ubuntu 22.04  
- Debian 10  
- Debian 11  
- EL 8 (Tested on Rocky Linux 8)  
- EL 9 (Tested on Rocky Linux 9)  
- Fedora 38  
- openSUSE 15.4

<!--
- List hardware requirements here  
-->

Role Variables
--------------

Variable | Default | Description
--- | --- | ---
`flatpak_enable_flathub_repo` | `true` | Whether to add the Flathub repository
`flatpak_flathub_repo_url` | `https://flathub.org/repo/flathub.flatpakrepo` | The URL of the Flathub repository
`flatpak_install_gnome` | `false` | Whether to install the GNOME Software plugin
`flatpak_install_kde` | `false` | Whether to install the KDE Discover plugin
`flatpak_packages` | `[]` | List of flatpak packages to install
`flatpak_user` | `{{ ansible_user_id }}` | The user to install flatpak packages for
`flatpak_user_packages` | `[]` | List of flatpak packages to install for the the user
`flatpak_uninstall_packages` | `[]` | List of flatpak packages to uninstall
`flatpak_user_uninstall_packages` | `[]` | List of flatpak packages to uninstall for the the user
<!--
`variable` | `default` | Variable example
`long_variable` | See [defaults/main.yml](./defaults/main.yml) | Variable referring to defaults
`distro_specific_variable` | See [vars/debian.yml](./vars/debian.yml) | Variable referring to distro-specific variables
-->

Dependencies
------------
<!-- List dependencies on other roles or criteria -->
None

Example Playbook
----------------

```yaml
    - role: "diademiemi.flatpak"
      tags: ['diademiemi', 'flatpak', 'setup']    ```

```

License
-------

MIT

Author Information
------------------

- diademiemi (@diademiemi)

Role Testing
------------

This repository comes with Molecule tests for Docker on the supported platforms.
Install Molecule by running

```bash
pip3 install -r requirements.txt
```

Run the tests with

```bash
molecule test
```

These tests are automatically ran by GitHub Actions on push. If the tests are successful, the role is automatically published to Ansible Galaxy.
