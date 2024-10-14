# jpstack

**jpstack** is an opinionated, minimalistic custom installer for efficient userspace software. It automates the setup of a carefully curated selection of tools and configurations, streamlining the installation process across various Linux distributions.

## Philosophy

Linux is not the problem -- it is the poorly configured userspace environments that lead to inconsistencies and inefficiencies. **jpstack** solves this by delivering a reproducible, distro-agnostic setup with cherry-picked minimalist software and sane configuration defaults, ensuring a reliable and optimized system every time and avoiding the clutter of unnecessary packages.

## Core Components

- **jpwm**: A custom window manager designed for simplicity, robustness and speed.

- **jpte**: A terminal emulator built with minimalism in mind, prepared for the 21st century.

- **Colletion of *suckless* software**: Integration of lightweight tools such as `imv`, `bgs`,
  `vim`, `dmenu`, etc.

- **Dotfiles**: Configuration files that customize some userspace tools I use,
  such as `vim`, `gdb`, `ksh`, `bash` and a collection of scripts.

## Opionated System Configuration

### Networking

- **NetworkManager**: Standardized across distros for seamless network management.

- **Bridge Networking**: Configured to use a master-slave network interface paradigm.
    - **Bridge Master**: All network interfaces are configured to pass through a
      bridge master, providing complete Layer 2 communication.
    - **Virtual Machines**: This configuration allows VM interfaces to communicate 
      without NAT, using real IP addresses for direct access.

## Features

- **Cross-Distro Compatibility**: Works with multiple Linux distributions, so you
  can set up your environment no matter what system you’re running.

- **Idempotent Configuration**: Re-running jpstack doesn’t change anything already
  configured; it will only make the required updates.

- **Modular Architecture**: Organized into stages, allowing you to select which 
  parts of the system to configure.

## Installation

1. **Clone the Repository**:
```sh
git clone https://github.com/yourusername/jpstack.git
cd jpstack
```

2. **Install Ansible**
Follow [Ansible's official installation](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html) guide to get started.

3. **Configure Inventory**

Edit inventory.ini to specify which stages of installation you want to run.
```ini
[local:vars]
stages_to_run=stage_0,stage_1,stage_2,stage_3,stage_4
```

4. **Run the Playbook**
```sh
ansible-playbook playbook.yml -Kv
```
