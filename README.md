# Getting Start with Ansible
This is a brief set of instructions to get an environment ready for Ansible.  The starting point is from a new distribution setup.  In my example, am using Ubuntu 20.04 LTS.

## Get the latest updates for the Linux distribution
* `sudo apt update`
* `sudo apt -y upgrade`

## Install Linux Packages
Run the commands below to install packages for git and ansible.
* `sudo apt install -y git`
* `sudo apt install -y python3-pip`
* `sudo add-apt-repository --yes --update ppa:ansible/ansible`
* `sudo apt install -y ansible`

## Clone the Aruba AOS-CX Ansible Collection
A directory call `aoscx-ansible-collection` will be created and will have the necessary files to continue with setting up Ansible when you run the next command
* `git clone https://github.com/aruba/aoscx-ansible-collection.git`

### Change to the `aoscx-ansible-collection` directory to run the next set of commands
* `cd ./aoscx-ansible-collection`
* `ansible-galaxy install -r requirements.yml`
* `python3 -m pip install -r requirements.txt`

### Intall the AOS-CX collections
* `ansible-galaxy collection install arubanetworks.aoscx`