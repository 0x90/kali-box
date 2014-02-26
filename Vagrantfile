# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "kali"

  config.vm.provider :parallels do |parallels|
    parallels.customize ["set", :id, "--memsize", "1024"]
  end

  config.vm.provider :virtualbox do |vb|
    vb.customize ["modifyvm", :id, "--memory", "2048"]
    vb.customize ["modifyvm", :id, "--cpuexecutioncap", "65"]
    vb.gui = true
  end

  config.vm.provider "vmware_fusion" do |v, override|
    override.vm.box = "precise64_fusion"
  end

  config.ssh.forward_x11 = true

  config.vm.provision "shell", path: "scripts/updatepackages.sh"
  config.vm.provision "shell", path: "scripts/metasploit.sh"

end

