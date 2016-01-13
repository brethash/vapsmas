#Ansible + Magento + Apache Solr#

##PREREQUISITES##
**1.) Install Vagrant**

```
#!bash

https://www.vagrantup.com/downloads.html
```

**2.) Install VirtualBox**


```
#!bash

https://www.virtualbox.org/wiki/Downloads
```

##HOW TO USE##
**0.) Clone this repository and then cd into it. Obviously...**

**1.) Copy playbook.yml.template to playbook.yml.**

**1.5) If your ssh key is not in ~/.ssh/id_rsa, add the following line under the vars section in playbook.yml**
```
#!bash

git_public_key: "{path/to/your/public_key.pub}"
git_private_key: "{path/to/your/private_key}"
```

**2.) Vagrant up! (you may have to enter your computer password a couple times during provisioning)**

```
#!bash

vagrant up
```

**3.) Once provisioning is complete, you should be able to access the site at http://magento.local**
