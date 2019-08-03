# -*- mode: ruby -*-
# vi: set ft=ruby :


Vagrant.configure("2") do |config|
  
  config.vm.define "db_centos7" do |db|
    db.vm.box = "centos/7"
    db.vm.provider "virtualbox" do |vb|
    vb.name = "db_centos7"
    end
    db.vm.network "private_network", ip: "192.168.56.30"
    db.vm.network "forwarded_port", guest: 3306, host: 3306
    db.vm.provision "shell", path: "scenario_db.sh"
  end

  config.vm.define "web_centos7" do |web|
    web.vm.box = "centos/7"
    web.vm.provider "virtualbox" do |vb|
    vb.name = "web_centos7"
    end
    web.vm.network "private_network", ip: "192.168.56.20"
    web.vm.provision "shell", path: "scenario_web.sh"
  end

end


