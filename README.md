tmux-conf
=========

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-tmux-conf.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-tmux-conf)

Install your tmux config hosted on the Github.

Requirements
------------

* [motemen/ghq](https://github.com/motemen/ghq)

The directory structure of the repository where your tmux config is hosted must be in the following manner.

```
(repository root)/
  .tmux.conf
```

Role Variables
--------------

* ghq_executable: The executable path of ghq command. The default is "ghq".
* remote_repository_path: The remote repository where your tmux config is hosted.

Dependencies
------------

* [suzuki-shunsuke.ghq-module](https://galaxy.ansible.com/suzuki-shunsuke/ghq-module/)

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.tmux-conf
    remote_repository_path: suzuki-shunsuke/tmux.conf
    ghq_executable: /home/vagrant/.go/bin/ghq
```

License
-------

MIT
