# dotfiles

Automated terminal configuration using [chezmoi](https://www.chezmoi.io/) and [Ansible](https://docs.ansible.com/).

## Config

Emulator - [Kitty](https://sw.kovidgoyal.net/kitty/)

Prompt - [Starship](https://starship.rs/)

Editor - [LazyVim](https://www.lazyvim.org/)

## Prerequisites

This repository is designed to automate configuration of the terminal only, *not* a full-fledged developer environment. The target machine is assumed to have the following programs installed.

### MacOS

Homebrew - `/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

Git - `brew install git`

Ansible -`brew install ansible`

### Ubuntu

Cargo - `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`

Git - `sudo apt install git`

Ansible - `sudo apt install ansible`

## Installation

```shell
sh -c "$(curl -fsLS get.chezmoi.io/lb)" -- init --apply --ssh henrynoyes
```

## Uninstallation

Run the appropriate rollback playbook manually with,
```shell
ansible-playbook playbooks/rollback_{macos|ubuntu}.yml
```

Then purge chezmoi with,
```shell
chezmoi purge --binary
```

## Inspiration

[The ultimate dotfiles setup | Singularity Club](https://www.youtube.com/watch?v=-RkANM9FfTM)