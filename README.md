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
$ A_HOME=~; A_UID=$(id -un); A_GID=$(id -gn) \
  && sudo ansible-pull -U https://github.com/bearcodi/desktop.git \
  --extra-vars "{\"home\": \"$A_HOME\", \"uid\": \"$A_UID\", \"gid\": \"$A_GID\"}"
```

> **SECURITY** The `https` version of the repository URL for security purposes makes the repository `read-only` by default
