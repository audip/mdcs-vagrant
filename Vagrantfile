Vagrant.configure(2) do |config|

  # Ensure ubuntu vm has the latest version of VirtualBox Guest Additions
  # (Requires vagrant-vbguest plugin)
  config.vbguest.auto_update = true

  # The IP Address ends in 14.4 to indicate 14.04, Update it when we change versions
  config.vm.network "private_network", ip: "192.168.14.4"

  config.vm.box = "ubuntu-14.04-amd64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"

  # Disable the default shared directory
  #config.vm.synced_folder ".", "/vagrant", disabled: true
  # Instead share our parent directory to /vagrant
  config.vm.synced_folder ".", "/vagrant", create: true

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  config.vm.provider "virtualbox" do |vb|
    # Needs atleast 1 Gig of memory
    vb.memory = "1024"

    # Stackoverflow says this is required to give the virtualbox internet access
    vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
  end
end

