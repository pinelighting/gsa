# Getting Start with Ansible
This is a brief set of instructions to get an environment ready for Ansible.  The starting point is from a new distribution setup.  In my example, I am using Ubuntu 20.04 LTS.

## Get the latest updates for the Linux distribution
* `sudo apt update; sudo apt -y upgrade`

## Install Linux Packages
Run the commands below to install packages for git and ansible.
* `sudo add-apt-repository --yes --update ppa:ansible/ansible`
* `sudo apt install -y git python3-pip ansible`

## Clone the Aruba AOS-CX Ansible Collection
A directory call `aoscx-ansible-collection` will be created and will have the necessary files to continue with setting up Ansible when you run the next command
* `git clone https://github.com/aruba/aoscx-ansible-collection.git`

### Change to the `aoscx-ansible-collection` directory to run the next set of commands
* `cd ./aoscx-ansible-collection`
* `ansible-galaxy install -r requirements.yml`
* `python3 -m pip install -r requirements.txt`
* `ansible-galaxy collection install arubanetworks.aoscx`

At this point, the installation is complete and your Ansible control node is ready.


### Info from my running system:
```
ubuntu-server:~$ ansible --version
ansible [core 2.11.6]
  config file = /etc/ansible/ansible.cfg
  configured module search path = ['/home/michaelw-test/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/lib/python3/dist-packages/ansible
  ansible collection location = /home/michaelw-test/.ansible/collections:/usr/share/ansible/collections
  executable location = /usr/bin/ansible
  python version = 3.8.10 (default, Sep 28 2021, 16:10:42) [GCC 9.3.0]
  jinja version = 2.10.1
  libyaml = True
  ```
### Quick ansible validation
```
ubuntu-server:~$ ansible localhost -m ping
localhost | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```