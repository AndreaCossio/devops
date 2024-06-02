# Ansible playbooks

This guide will demonstrate how to set up Ansible.

## Ansible installation

[Here](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) you can find the official guide for installing Ansible.

Some key steps are:

- Install Python 3.9+ on the local machine and the VMs (`sudo apt-get install python3`)
- Install Ansible on the control node (`pip install ansible`)

*Optional*: Install linter by running `pip install ansible-lint`.

### Configuration

[Here](https://docs.ansible.com/ansible/latest/reference_appendices/config.html) you can find the official guide for configuring Ansible.

To create the config file, run the following command:

```bash
touch ansible.cfg
```

> Note, it is **best practice** to place the config file in `/etc/ansible`.

Then, update the content of `ansible.cfg`:

```ini
[defaults]
inventory = ./inventory.yaml
```

> Example: [ansible.cfg](./ansible.cfg)

Finally, place the `inventory.yaml` in the same folder. Test the configuration running:

```bash
ansible all --list-hosts
```

You can also try to ping all the hosts:

```bash
ansible all -m ping
```
