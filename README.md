#Ansible + Magento + Apache Solr#

##PREREQUISITES##
**1.) Install Vagrant**

```
https://www.vagrantup.com/downloads.html
```

**2.) Install VirtualBox**


```
https://www.virtualbox.org/wiki/Downloads
```

##HOW TO USE##
0. Clone this repository and then cd into it. Obviously...

1. Duplicate playbook.yml.template and rename it to playbook.yml.

2. Vagrant up! (you may have to enter your computer password a couple times during provisioning)

```
vagrant up
```

3. Once provisioning is complete, you should be able to access the site at http://magento.local

* **OPTIONAL** If your ssh key is not in ~/.ssh/id_rsa, add the following line under the vars section in playbook.yml
```
git_public_key: "{path/to/your/public_key.pub}"
git_private_key: "{path/to/your/private_key}"
```