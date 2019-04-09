# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|

    config.vm.box = "geerlingguy/centos7" #CentOS 7
    config.vm.network "private_network", ip: "192.168.123.123"
    
    config.vm.provision "shell", inline: <<-SHELL
    yum clean all
    yum install epel-release -y
    yum update -y
    yum groupinstall -y "Development Tools" -y
    yum install -y httpd httpd-devel pcre pcre-devel libxml2 libxml2-devel curl curl-devel openssl openssl-devel nano -y
    SHELL
    config.vm.provision :shell, path: "install.sh"
    config.vm.provider "virtualbox" do |v|
      v.memory = 4096
      v.cpus = 4
    end
    config.vm.provision:reload
  end
  
  