# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
  config.vm.box = "ubuntu/bionic64"
  config.ssh.forward_x11 = true

  # Mount host's ./shared_data at /home/vagrant/shared_data in guest.
  config.vm.synced_folder "./shared_data", "/home/vagrant/shared_data"
  # disable default mouting of project directory
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider "virtualbox" do |vb|
    vb.memory = 512
    vb.cpus = 1
  end

  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y software-properties-common wget
    # based on https://typora.io/#linux
    sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
    sudo add-apt-repository 'deb https://typora.io/linux ./'
    sudo apt-get update
    sudo apt-get dist-upgrade
    sudo apt-get install -y typora libgtk-3-0 libxss1 libnss3 libasound2
  SHELL
end
