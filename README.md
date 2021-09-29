# Getting Start with Ansible
This is a brief set of instructions to get an environment ready for Ansible.  The starting point is from a new distribution setup.  In my example, I am using Ubuntu 20.04 LTS.

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

At this point, the installation is complete and your Ansible control node is ready.


### Info from my running system:
```
ubuntu-server:~$ ansible --version
ansible 2.9.6
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/home/michaelw/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  executable location = /usr/bin/ansible
  python version = 3.8.10 (default, Jun  2 2021, 10:49:15) [GCC 9.4.0]
  ```
### Quick ansible validation
```
ubuntu-server:~$ ansible localhost -m ping
localhost | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```