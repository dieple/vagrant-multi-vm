# -*- mode: ruby -*-
# vi: set ft=ruby :
# Sample Vagranfile to setup Learning Environment
# for Ansible Playbook Essentials

#require_relative 'vagrant_rancheros_guest_plugin.rb'

# To enable rsync folder share change to false
$rsync_folder_disabled = false
$number_of_nodes = 1
$vm_mem = "1024"
$vb_gui = false



VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "ansible-ubuntu-1404-amd64"
  config.vm.box_url = "https://cloud-images.ubuntu.com/vagrant/trusty/current/trusty-server-cloudimg-amd64-vagrant-disk1.box"

  config.vm.define "control" do |control|
    control.vm.network :private_network, ip: "192.168.61.10"
  end

  config.vm.define "db" do |db|
    db.vm.network :private_network, ip: "192.168.61.11"
  end

  config.vm.define "dbel" do |db|
    db.vm.network :private_network, ip: "192.168.61.14"
    db.vm.box = "opscode_centos-6.5-i386"
    db.vm.box = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.5_chef-provisionerless.box"
  end

  config.vm.define "ansible" do |ansible|
    ansible.vm.network :private_network, ip: "192.168.61.16"
    ansible.vm.box = "opscode_centos-6.5-i386"
    ansible.vm.box = "http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_centos-6.5_chef-provisionerless.box"
  end

  config.vm.define "www" do |www|
    www.vm.network :private_network, ip: "192.168.61.12"
  end

  config.vm.define "lb" do |lb|
    lb.vm.network :private_network, ip: "192.168.61.13"
  end


end
