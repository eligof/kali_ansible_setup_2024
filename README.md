# Kali Linux Ansible Playbook setup
This is my personal Kali Linux setup that I install as a base for my fresh Kali Linux images. The only package required to get it up and running is ansible. 

This repository is constantly being updated with new packages and configurations. It can be used as a template to set up your own prefered Kali Linux installation. 

##
## How to run
Install Ansible as prerequisite, then run the ansible-playbook command and wait. 
```sh
Install Ansible (python3 -m pip install ansible)
Clone and enter the repo (git clone)
ansible-galaxy install -r requirements.yml (press y to install if asked)
Make sure we have a sudo token (sudo whoami)
sudo ansible-playbook kali-setup.yml
```
##
## Post configuration
After the playbook has finished, I would recommend rebooting the system and edit the zsh config file.
```sh
nano ~/.zshrc 
```
1) Set HISTSIZE=1000 to 300000 and SAVEHIST=2000 to 300000
2) At the and of the file add alias:
```sh
alias autorecon="sudo python3  /usr/share/privsec/autorecon/autorecon.py"
```
##

## files folder
Run ```locate privsec``` in the terminal to see where the files are located
##
## Possible issues
The playbook clones different Github repositories and downloads several release files from dynamic GitHub release pages. It's possible that one of the files is no longer available or that the location has changed. If it errors out, just change the URL's to the new correct file location. I added some additional error handling so it will not break the script. 
