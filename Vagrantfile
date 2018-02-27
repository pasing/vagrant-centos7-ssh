# -*- mode: ruby -*-
# vi: set ft=ruby :

# set vagrantfile api/syntax version
VAGRANTFILE_API_VERSION = "2"

# set docker as the default provider
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

# disable parallellism so that the containers come up in order
ENV['VAGRANT_NO_PARALLEL'] = "1"
ENV['FORWARD_DOCKER_PORTS'] = "1"

unless Vagrant.has_plugin?("vagrant-docker-compose")
  system("vagrant plugin install vagrant-docker-compose")
  puts "Dependencies installed, please try the command again."
  exit
end

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
config.vm.define "centos7-ssh" do |app|
  app.vm.provider "docker" do |d|
    d.build_dir = "."
    d.name = "centos7-ssh"
    d.has_ssh = true
  end
end
end
