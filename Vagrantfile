HOSTNAME = "magento.local"
PRIVATE_NETWORK_IP = "192.168.50.4"
VAGRANT_BOX = "ubuntu/trusty64"

### DO NOT EDIT BELOW THIS LINE ###

VAGRANTFILE_API_VERSION = "2"

$dependencies = <<SCRIPT
  echo Checking for Pip
  sudo easy_install pip
  echo Checking for Ansible
  sudo pip install ansible
SCRIPT

required_plugins = %w( vagrant-hostsupdater vagrant-host-shell vagrant-vbguest )
required_plugins.each do |plugin|
    exec "vagrant plugin install #{plugin};vagrant #{ARGV.join(" ")}" unless Vagrant.has_plugin? plugin || ARGV[0] == 'plugin'
end

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  
  config.vm.box = VAGRANT_BOX

  config.vm.network "private_network", ip: PRIVATE_NETWORK_IP

  config.vm.hostname = HOSTNAME

  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.synced_folder "www", "/var/www"

  config.vm.provision :host_shell do |host_shell|
    host_shell.inline = $dependencies
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
  end

end
