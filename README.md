# ROS Tooling Repository Configurations

This repository contains common resources for configuration of `ros-tooling` repositories, as well as the workflows to automatically apply desired configurations to the managed repos.
It attemps to implement the design at https://github.com/ros-tooling/design/blob/main/docs/github-repository-management.md

Some common sources may come from https://github.com/ros-tooling/.github, but the types of files that can be managed by that are very limited compared to the full list of configurations we want to manage.

## Features

### File sync

Uses a GitHub Action to apply files as a PR to managed repositories.
Some files can be applied via the https://github.com/ros-tooling/.github repository, but this only allows for a very specific set of files, limiting its usefulness.

See `.github/workflows/file-sync.yml` for details on managed repositories and synchronized files.

The managed files include workflows to auto-approve and auto-merge these file-sync PRs, if all required checks pass.

### Settings sync

TODO: Synchronize some repository configuration to managed repositories - useful for getting common configuration like "squash-merge only" and various Team access permissions.

## Contributing

Please add the following comment at the top of files to be synchronized - this is not done automatically.
This is similar to the `marker` concept of Ansible's [`blockinfile`](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/blockinfile_module.html)

```
# NOTE: this file is managed by ros-tooling/repo-configs, don't edit it manually.
```
