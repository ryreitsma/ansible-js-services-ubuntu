#### Installation
There are a few manual steps to take before you can run the Ansible script

### Create a personal access token for your Github account
You need the token to be able to install private Coolblue npm modules. See https://help.github.com/articles/creating-an-access-token-for-command-line-use/ on how to create the personal access token.

### Install Ansible
First of all, install a recent version of Ansible to run the script. There is an install script in the root of this repository, so just run:
```
sudo ./install_ansible.sh
```
### Configure Ansible variables
The Ansible script needs a few variables to configure the Ubuntu workstation properly. Since these variables are personal and sometimes even secret, this repository contains only contains an example file. Do not add your own configuration to this repository! Your Github token for example, should NEVER be shared with others.

In the root of this repository you'll find the variables.yml.example file which contains all variables. First create and copy the file to the correct location:
```
mkdir -p group_vars/all
cp variables.yml.example group_vars/all/main.yml
```

Then fill in the variables and run the Ansible playbook:

```
ansible-playbook playbook.yml -K
```

If you have additional steps to add or want to change some setup, a pull request is always welcome!
