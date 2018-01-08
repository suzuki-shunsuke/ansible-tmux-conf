# ansible-tmux-conf

[![Ansible Role](https://img.shields.io/ansible/role/d/12946.svg)](https://galaxy.ansible.com/suzuki-shunsuke/tmux-conf/)
[![Ansible Role](https://img.shields.io/ansible/role/12946.svg)](https://galaxy.ansible.com/suzuki-shunsuke/tmux-conf/)
[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-tmux-conf.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-tmux-conf)
[![GitHub last commit](https://img.shields.io/github/last-commit/suzuki-shunsuke/ansible-tmux-conf.svg)](https://github.com/suzuki-shunsuke/ansible-tmux-conf)

ansible role to install tmux configurations.

## Requirements

* git

## Role Variables

name | required | default | description
--- | --- | --- | ---
tmux_conf_repo | yes | |
tmux_conf_cloned_dest | yes | |
tmux_conf_version | no | HEAD |
tmux_conf_links | no | [] |

## Dependencies

Nothing.

## Example Playbook

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.tmux-conf
    tmux_conf_repo: "https://github.com/suzuki-shunsuke/tmux.conf"
    tmux_conf_cloned_dest: "{{ansible_env.HOME}}/repos/src/github.com/suzuki-shunsuke/tmux.conf"
    tmux_conf_version: mac
    tmux_conf_links:
      - src: "{{(ansible_os_family == 'Darwin')|ternary('mac', 'linux')}}_tmux.conf"
        dest: "{{ansible_env.HOME}}/.tmux.conf"
```

## License

[MIT](LICENSE)
