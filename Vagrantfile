# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure(2) do |config|

  # http://fgrehm.viewdocs.io/vagrant-cachier
  if Vagrant.has_plugin?("vagrant-cachier")
    config.cache.scope = :box
  else
    puts "Run 'vagrant plugin install vagrant-cachier' to speed up provisioning."
  end

  config.vm.hostname = "dspace"
  config.vm.box      = "ubuntu/trusty64"

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "site.yml"
    ansible.host_key_checking = false
    ansible.extra_vars = { ansible_ssh_user: "vagrant", testing: true }
  end

#  if ENV['SYNC_REPO']
#    config.vm.synced_folder ENV['SYNC_REPO'], "/srv/dspace-src"
#  end

  config.vm.post_up_message = "Welcome to your testing DSpace VM"

end
