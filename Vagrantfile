# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vm.synced_folder "./web_data", "/vagrant_web"
    config.vm.synced_folder "./db_data", "/vagrant_db"
    config.vm.synced_folder "./app_data", "/vagrant_app"

    config.vm.box = "ubuntu/focal64"

    config.vm.define "web" do |web|
        web.vm.hostname = "web"
        web.vm.network "private_network", ip: "192.168.56.101"
    
        web.vm.provider "virtualbox" do |vb|
            vb.name = "hr_service_web"
            vb.memory = "2048"
            vb.cpus = 2
        end

        web.vm.provision "shell", path: "provision/web.sh"
    end

    config.vm.define "db" do |db|
        db.vm.hostname = "db"
        db.vm.network "private_network", ip: "192.168.56.102"

        db.vm.provider "virtualbox" do |vb|
            vb.name = "hr_service_db"
            vb.memory = "1024"
            vb.cpus = 1
        end

        db.vm.provision "shell", path: "provision/db.sh"
    end

    config.vm.define "app" do |app|
        app.vm.hostname = "app"
        app.vm.network "private_network", ip: "192.168.56.103"

        app.vm.provider "virtualbox" do |vb|
            vb.name = "hr_service_app"
            vb.memory = "2048"
            vb.cpus = 2
        end

        app.vm.provision "shell", path: "provision/app.sh"
    end
end
