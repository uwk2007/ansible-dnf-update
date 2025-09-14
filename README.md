![Ansible Compatible](https://img.shields.io/badge/Ansible-compatible-green)
![Enterprise Linux DNF](https://img.shields.io/badge/Enterprise_Linux_DNF-compatible-green)

# Ansible Role: dnf-update

> ℹ️ **Note**  
> A detailed tutorial is available at: [https://www.filipnet.de/ansible-dnf-update](https://www.filipnet.de/ansible-dnf-update)

This Ansible role updates Enterprise Linux hosts (RHEL, CentOS, AlmaLinux, Rocky) using **dnf**, logs the system state before and after updates, generates diffs, and optionally sends a mail report.

Note: This role supports the automatic creation of snapshots for Proxmox LXC containers and QEMU virtual machines.
It requires an additional role, which will be documented in a follow-up tutorial.

- Further information and usage details can be found in the tutorial:
  https://www.filipnet.de/ansible-proxmox-snapshot/

- The role’s source code is available on GitHub:
  https://github.com/filipnet/ansible-proxmox-snapshot

## Table of contents

<!-- TOC -->

- [Ansible Role: dnf-update](#ansible-role-dnf-update)
  - [Table of contents](#table-of-contents)
  - [Features](#features)
  - [Role Variables](#role-variables)
  - [Example Playbook](#example-playbook)
  - [Contributions](#contributions)
  - [License](#license)

<!-- /TOC -->

## Features

- **Update packages** using `dnf`
- **Log system state** before and after updates (installed packages, running services)
- **Generate diffs** for packages and services
- **Timestamped logs** stored in `/var/log/dnf-update`
- **Optional system reboot** after update
- **Optional Proxmox snapshot** before update
- **Optional email report** with diffs included in the mail body
- **Optional dry-run mode** for testing

## Role Variables

Main variables can be configured in `defaults/main.yml`.  
**Recommendation:** Define them in `group_vars/all.yml` or a group-specific vars file.  
Configuring them per host is possible but not efficient, since you would have to set them on every single system you want to update.

## Example Playbook

Create a playbook `update.yml`:

Here is an example of how to run the role against all Red Hat–based VMs and LXC containers.

```yaml
- hosts: all
  become: yes
  roles:
    - role: dnf-update
      when: ansible_os_family == "RedHat"
```

If you want to run it against a specific host instead of all hosts in your inventory, use the -l (limit) flag.

```bash
ansible-playbook update.yml -l myserver.example.com
```

You can also use an IP address:

```bash
ansible-playbook update.yml -l 192.168.1.10
```

Or run it against multiple hosts separated by commas:

```bash
ansible-playbook update.yml -l "web01,db02"
```

Or limit to an inventory group:

```bash
ansible-playbook update.yml -l production
```

Or if you use a specific inventory

```bash
ansible-playbook -i inventory/example update.yml -l web01.examplecorp.io
```

## Contributions

Contributions are welcome! If you would like to improve this project, please feel free to submit a pull request. All contributions, bug reports, and feature suggestions are appreciated.

## License

`dnf-update` and all individual scripts are under the **BSD 3-Clause license** unless explicitly noted otherwise. See the [LICENSE](./LICENSE) file for more details.
