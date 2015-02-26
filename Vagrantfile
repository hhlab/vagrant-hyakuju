# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  # Refs http://www.vagrantbox.es/
  config.vm.box = "https://f0fff3908f081cb6461b407be80daf97f07ac418.googledrive.com/host/0BwtuV7VyVTSkUG1PM3pCeDJ4dVE/centos7.box"

  # Refs http://qiita.com/hapicky/items/a7f9d56588f96d005fad
  # 初回起動時はコメントアウト
  # config.vbguest.auto_update = false

  config.vm.define :web do |web|
    web.vm.network :private_network, ip: "192.168.110.10"
    web.vm.hostname = "www.hyakuju"

    web.vm.provider "virtualbox" do |vb|
      vb.name = "www.hyakuju"
      vb.memory = 512
    end
  end

  config.vm.define :db do |db|
    db.vm.network :private_network, ip: "192.168.110.20"
    db.vm.hostname = "db.hyakuju"

    db.vm.provider "virtualbox" do |vb|
      vb.name = "db.hyakuju"
      vb.memory = 512
    end
  end
end
