# Desktop setup automation

Ansible stuffs for setting up my desktop environment from fresh install

> Currently based on Ubuntu 18.04.3 LTS

## Install ansible

```bash
$ sudo apt-get install -y software-properties-common git \
  && sudo apt-add-repository -y ppa:ansible/ansible \
  && sudo apt-get update \
  && sudo apt-get install -y ansible
```

## Run the ansible playbook

The `ansible-pull` command uses the `-U` option, which expects a repository URL. We don't need to specify a filename for the playbook to run as ansible will automatically look for `local.yml` in the root of the repository.

```bash
$ sudo ansible-pull -U https://github.com/bearcodi/desktop.git \
  --extra-vars "{\"home\": \"$HOME\", \"uid\": \"$USER\", \"gid\": \"$USER\"}"
```

> **SECURITY** The `https` version of the repository URL for security purposes makes the repository `read-only` by default

## Standard packages
 - [ ] gnome-tweaks
 - [x] git
 - [x] terminator
 - [x] htop
 - [x] httpie
 - [x] wget
 - [ ] zsh with theme

## Development environment

 - [x] Docker
 - [x] ctop
 - [ ] Docker-Compose
 - [ ] MySql Workbench
 - [x] Vim
 - [ ] Atom
 
## OS customisations
 - [x] Custom wallpaper
 - [x] Custom lockscreen
 - [x] Custom theme (Arc-Dark)
 - [ ] Auto hide dock
 - [ ] Position dock at bottom
 - [ ] Workspaces span displays
 - [ ] Top bar show date, seconds and week numbers in calendar
 
