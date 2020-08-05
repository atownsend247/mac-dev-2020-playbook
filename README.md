# Mac Development Ansible Playbook

![Mac Dev 2020 Playbook Logo](https://raw.githubusercontent.com/atownsend247/mac-dev-2020-playbook/master/files/markdown_logo.png)

This playbook installs and configures most of the software I use on my Mac for web and software development. Some things in macOS are slightly difficult to automate, so I still have some manual installation steps, but at least it's all documented here. The items installed within this playbook have been inspired by the [How to Set Up Your MacBook for Web Development in 2020](https://medium.com/better-programming/setting-up-your-mac-for-web-development-in-2020-659f5588b883) article credit where credit is due.

This is a work in progress, and is mostly a means for me to document my current MacBook Pro's setup. I'll be evolving this set of playbooks over time.

*See also*:

- [How to Set Up Your MacBook for Web Development in 2020](https://medium.com/better-programming/setting-up-your-mac-for-web-development-in-2020-659f5588b883)

## Installation

  1. Ensure the Homebrew package manager is installed (`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install.sh)"` to launch the installer).
  2. [Install Ansible](http://docs.ansible.com/intro_installation.html).
  3. Clone this repository to your local drive.
  4. Run `$ ansible-galaxy install -r requirements.yml` inside this directory to install required Ansible roles.
  5. Run `ansible-playbook -i inventory.local inventory.local.yml -KDC` inside this directory. Enter your account password when prompted. Check over the changes (checkmode)
  6. Run `ansible-playbook -i inventory.local inventory.local.yml -KD` inside this directory. Enter your account password when prompted. Apply the changes (non-checkmode)

> Note: During the installation, you might be asked to install the Xcode Command Line Tools if you haven’t already. Just follow the instructions on the screen.
> Note: If some Homebrew commands fail, you might need to agree to Xcode's license or fix some other Brew issue. Run `brew doctor` to see if this is the case.

## Included Applications / Configuration (Default)

Applications (installed with Homebrew Cask):

- [Docker](https://www.docker.com/)
- [iterm2](https://www.iterm2.com/)
- [rectangle](https://rectangleapp.com/)
- [visual-studio-code](https://code.visualstudio.com/)

Packages (installed with Homebrew):

- docker-compose
- git
- htop
- node
- romkatv/powerlevel10k/powerlevel10k
- zsh
- zsh-syntax-highlighting
- zsh-autosuggestions
- zsh-history-substring-search

## Future additions

### Things that still need to be done manually

It's my hope that I can get the rest of these things wrapped up into Ansible playbooks soon, but for now, these steps need to be completed manually (assuming you already have Xcode and Ansible installed, and have run this playbook).

  1. placeholder for future addtions tweaks.

### TODO

  1. My hope is to get this plugged into a CI/CD pipeline for testing
