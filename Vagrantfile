# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "precise64"
  config.vm.hostname = "test.rcos.rpi.edu"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.network :private_network, ip: "192.168.56.2"

  config.vm.provider :virtualbox do |vb|
      vb.customize [
        "modifyvm", :id,
        "--memory", "2048",
        "--cpus", "4"]
  end

  config.vm.provision :puppet do |puppet|
     puppet.manifests_path = "puppet"
     puppet.manifest_file  = "base.pp"
     puppet.module_path    = "modules"
     puppet.options        = ""
  end
end