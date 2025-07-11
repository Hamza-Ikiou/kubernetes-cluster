# Ansible User Guide

### Installing pipx
To install Ansible, you will need pipx on your system, please refer to the official documentation : [pipx installation](https://pipx.pypa.io/stable/)

### Installing ansible
Once pipx is available, you can install Ansible with the following commands :

Full ansible package :

```bash
pipx install --include-deps ansible
```

Minimal ansible-core package :

```bash
pipx install ansible-core
```

You can verify the installation with :

```bash
ansible --version
```

For more information, see the official documentation : [Ansible Installation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)

## Launch the playbook
Before you start the playbook, make sure to insert the path to the ssh_key that will ensure the connection to you virtual machines in the `inventory/group_vars/all.yml` file !

Once Ansible is installed, you can start the playbook with the following command :

```bash
ansible-playbook setup-cluster.yml
```

You can specify the vault password, if you have encrypted some files :

```bash
ansible-playbook setup-cluster.yml --ask-vault-pass
```

## Vault encryption
To encrypt a file, you can type the following command and insert a password :

```bash
ansible-vault encrypt inventory/group_vars/all.yml
```

To decrypt a file, you can type the following command and insert the corresponding password :

```bash
ansible-vault decrypt inventory/group_vars/all.yml
```