# Gnome-Terminal

[![Alma9-CI](https://github.com/philnewm/ansible-gnome-terminal/actions/workflows/alma9-ci-caller.yml/badge.svg)](https://github.com/philnewm/ansible-gnome-terminal/actions/workflows/alma9-ci-caller.yml) [![Rocky9-CI](https://github.com/philnewm/ansible-gnome-terminal/actions/workflows/rocky9-ci-caller.yml/badge.svg)](https://github.com/philnewm/ansible-gnome-terminal/actions/workflows/rocky9-ci-caller.yml) [![CentOSStream9-CI](https://github.com/philnewm/ansible-gnome-terminal/actions/workflows/centosstream9-ci-caller.yml/badge.svg)](https://github.com/philnewm/ansible-gnome-terminal/actions/workflows/centosstream9-ci-caller.yml) [![Debian12-CI](https://github.com/philnewm/ansible-gnome-terminal/actions/workflows/debian12-ci-caller.yml/badge.svg)](https://github.com/philnewm/ansible-gnome-terminal/actions/workflows/debian12-ci-caller.yml) [![Ubuntu2204-CI](https://github.com/philnewm/ansible-gnome-terminal/actions/workflows/ubuntu2204-ci-caller.yml/badge.svg)](https://github.com/philnewm/ansible-gnome-terminal/actions/workflows/ubuntu2204-ci-caller.yml)

Role description

This role includes a full vagrant based molecule testing setup at `molecule/default`

## Structure

```code
📦 ansible-gnome-terminal
 ┣ 📂 defaults
 ┃ ┗ 📜 main.yml
 ┣ 📂 meta
 ┃ ┗ 📜 main.yml
 ┣ 📂 molecule
 ┃ ┗ 📂 default
 ┃   ┗ 📜, 📜, 📜, scenario_files
 ┣ 📂 tasks
 ┃ ┣ 📜 main.yml
 ┃ ┣ 📜 present.yml
 ┃ ┣ 📜 dependencies.yml
 ┃ ┣ 📜 profile.yml
 ┃ ┣ 📜 absent.yml
 ┃ ┗ 📜 init.yml
 ┣ 📂 vars
 ┃ ┗ 📜 main.yml
 ┗ 🗒️ README.md
 ┗ 📓 requirements.txt

```

Describe and explain role structure.

## Requirements

This role needs an installed gnome desktop environment to be functional.

## Role Variables

* defaults/main.yml
  * gnome_terminal_package - terminal package name per linux os family
  * custom_profile - custom profile switch
  * terminal_profile_uuid - expected custom profile uuid
  * gnome_terminal_settings - general terminal settings
  * terminal_profile_path - profile dconf path contructed using `terminal_profile_uuid`
  * terminal_profile_settings - profile specific settings
* vars/main.yml
  * dependencies - to enable all features of this role

## Dependencies

This role doesn't depend on any additional ansible-galaxy roles

## Example Playbook

```yaml
---

tasks:
  - name: Include ansible-gnome-terminal present
    ansible.builtin.include_role:
      name: ansible-gnome-terminal
    vars:
      gnome_terminal_state: present
      custom_profile: true

...
```

## License

Add license - if any.
