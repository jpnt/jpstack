# jpstack

**jpstack** is a custom installer for a set of efficient userspace software.

It is designed to streamline the installation process and configuration of essential
tools I use in my environment, across multiple Linux distributions.

## Philosophy

99% of Linux problems are not Linux problems but userspace problems; Poorly configured
and bloated userspace software environments lead to the majority of the problems and inconsistencies.

Configuring a set of quality software is time consuming, even if you know what you are
doing, you will eventually forget some things.

My solution to this problem is to create a distro-agnostic reproducible environment with
a set of cherry-picked quality software. What I call: "jpstack".

## Features

- **Extensive Tooling**: Automates the installation of a variety of essential tools and
 applications.

- **Cross-Distro Compatibility**: Designed to support a multiple of Linux distros,
 allowing users to easily set up their environment on different systems. (Support for FreeBSD
 is also planned).
  
- **Declarative Configuration**: Utilizes **Ansible** as the automation tool to provide
 a clear and maintainable configuration structure.

- **Idempotent Operations**: Ensures that repeated executions of the installation process
 do not alter the system's state if it is already in the desired configuration.

- **Modular Architecture**: Organized into roles and tasks, making it easy to manage and
 extend. Each role encapsulates a specific aspect of the installation process.

- **Stage Selection**: Allows the user to select only the desired stages to run. Useful if
 OS is already installed in disk.

## Installation

To get started with jpstack, follow these steps:

1. **Clone the Repository**:

```sh
git clone https://github.com/yourusername/jpstack.git
cd jpstack
```

2. **Install Ansible**

```
https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html
```

3. **Configure Inventory**

```
Select the stages you want to run inside of inventory.ini.
```

4. **Run the Playbook**

```sh
ansible-playbook playbook.yml -Kv
```
