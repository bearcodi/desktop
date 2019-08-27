# Desktop setup automation

Ansible stuffs for setting up my desktop environment from fresh install

> Currently based on Ubuntu 18.04.3 LTS

## Install ansible

```bash
$ sudo apt-get install -y software-properties-common \
  sudo apt-add-repository -y ppa:ansible/ansible \
  sudo apt-get update 
  sudo apt-get install -y ansible
```

## Clone this repo and run playbook

```bash
$ git clone https://github.com/bearcodi/desktop.git ~/.desktop && cd ~/.desktop
```
