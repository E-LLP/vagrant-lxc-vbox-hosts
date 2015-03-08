# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  # Comment out if you don't have plans to use https://github.com/fgrehm/vagrant-cachier
  config.cache.scope = :box
  config.cache.auto_detect = true

  config.vm.provider :virtualbox do |vb|
    vb.customize [ "modifyvm", :id, "--memory", 1536, "--cpus", "2" ]
  end

  # Choose any Vagrant version from 1.2.0 to 1.6.3
  config.vm.provision :shell, path: 'provisioning/install-vagrant.rb', args: "'1.6.3'"
  config.vm.provision :shell, path: 'provisioning/install-vagrant-lxc.sh', args: "'1.0.1'"

  config.vm.define :precise do |ubuntu|
    ubuntu.vm.box     = 'precise64'
    ubuntu.vm.box_url = 'http://files.vagrantup.com/precise64.box'
    ubuntu.vm.provision :shell, path: 'provisioning/debian/install-dependencies.sh'
  end

  config.vm.define :quantal do |ubuntu|
    ubuntu.vm.box     = 'quantal64'
    ubuntu.vm.box_url = 'https://github.com/downloads/roderik/VagrantQuantal64Box/quantal64.box'
    ubuntu.vm.provision :shell, path: 'provisioning/debian/install-dependencies.sh'
  end

  config.vm.define :raring do |ubuntu|
    ubuntu.vm.box = 'raring64'
    ubuntu.vm.box_url = "http://cloud-images.ubuntu.com/vagrant/raring/current/raring-server-cloudimg-amd64-vagrant-disk1.box"
    ubuntu.vm.provision :shell, path: 'provisioning/debian/install-dependencies.sh'
  end

  config.vm.define :saucy do |ubuntu|
    ubuntu.vm.box = 'saucy64'
    ubuntu.vm.box_url = 'http://puppet-vagrant-boxes.puppetlabs.com/ubuntu-1310-x64-virtualbox-puppet.box'
    ubuntu.vm.provision :shell, path: 'provisioning/debian/install-dependencies.sh'
  end

  config.vm.define :trusty do |ubuntu|
    ubuntu.vm.box = 'trusty64'
    ubuntu.vm.box_url = 'http://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box'
    ubuntu.vm.provision :shell, path: 'provisioning/debian/install-dependencies.sh'
  end

  config.vm.define :wheezy do |debian|
    debian.vm.box = 'wheezy64'
    debian.vm.box_url = 'http://puppet-vagrant-boxes.puppetlabs.com/debian-70rc1-x64-vbox4210.box'
    debian.vm.provision :shell, path: 'provisioning/debian/install-dependencies.sh'
    debian.vm.provision :shell, path: 'provisioning/debian/configure-bridge.sh'
  end

  config.vm.define :fedora19 do |fedora|
    fedora.vm.box = 'fedora19'
    fedora.vm.box_url = 'https://dl.dropboxusercontent.com/u/86066173/fedora-19.box'
    fedora.vm.provision :shell, path: 'provisioning/fedora/install-dependencies.sh'
    fedora.vm.provision :shell, path: 'provisioning/fedora/configure-bridge.sh'

    # Disable NFS for fedora as the base box we are using does not seem
    # to support it
    fedora.vm.synced_folder ".", "/vagrant", id: 'vagrant-root', nfs: false
  end
end
