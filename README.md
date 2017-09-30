# ansible-tmux-conf

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-tmux-conf.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-tmux-conf)

ansible role to install tmux configurations

## Requirements

* git

## Role Variables

name | required | default | description
--- | --- | --- | ---
tmux_conf_repo | yes | |
tmux_conf_cloned_dest | yes | |
tmux_conf_version | no | HEAD |
tmux_conf_links | no | {} |

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
      tmux.conf: "{{ansible_env.HOME}}/.tmux.conf"
```

## License

[MIT](LICENSE)
