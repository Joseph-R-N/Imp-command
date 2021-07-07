# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.
  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "ubuntu/xenial64"
  config.vm.define "pragra-ansible" do |pa|
    pa.vm.hostname = "ansible-master"
    pa.vm.network "private_network", ip: "192.168.56.101"
    pa.vm.synced_folder ".", "/app-data"
     config.vm.provider :virtualbox do |vb|
       vb.customize ["modifyvm", :id, "--memory", "2048"]
       vb.customize ["modifyvm", :id, "--cpus", "2"]
    end
  end
  config.vm.define "pragra-app1" do |app1|
    app1.vm.hostname = "app1"
    app1.vm.network "private_network", ip: "192.168.56.102"
    #app1.vm.network "forwarded_port" , guest:8080 , host: 5001
     config.vm.provider :virtualbox do |vb|
       vb.customize ["modifyvm", :id, "--memory", "512"]
    end
  end
  config.vm.define "pragra-app2" do |app2|
    app2.vm.hostname = "app2"
    app2.vm.network "private_network", ip: "192.168.56.202"
    #app2.vm.network "forwarded_port" , guest:8080 , host: 5002
     config.vm.provider :virtualbox do |vb|
       vb.customize ["modifyvm", :id, "--memory", "512"]
    end
  end
  config.vm.define "pragra-app3" do |app3|
    app3.vm.hostname = "app3"
    app3.vm.network "private_network", ip: "192.168.56.201"
    #app2.vm.network "forwarded_port" , guest:8080 , host: 5002
     config.vm.provider :virtualbox do |vb|
       vb.customize ["modifyvm", :id, "--memory", "512"]
    end
  end
  config.vm.define "pragra-lb" do |lb|
    lb.vm.hostname = "lb"
    lb.vm.network "private_network", ip: "192.168.56.104"
    #lb.vm.network "forwarded_port" , guest:80 , host: 5000
     config.vm.provider :virtualbox do |vb|
       vb.customize ["modifyvm", :id, "--memory", "512"]
    end
  end
  config.vm.define "pragra-db" do |db|
    db.vm.hostname = "db"
    db.vm.network "private_network", ip: "192.168.56.105"
     config.vm.provider :virtualbox do |vb|
       vb.customize ["modifyvm", :id, "--memory", "512"]
    end
      end
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update -y
    apt-get install -y python-minimal
  SHELL
end
