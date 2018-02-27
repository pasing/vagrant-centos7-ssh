# Vagrant Docker Provider Image [Centos7-SSH]

Based on [CentOS-Dockerfiles](https://github.com/CentOS/CentOS-Dockerfiles/tree/master/ssh/centos7)

Modified by [Mattew Cwarman](https://raw.githubusercontent.com/mcwarman/vagrant-docker-provider/)


## Usage

Use `d.image` is required in `Vagrantfile` if you want use docker pre-build image.
Otherwise use `d.build_dir` for  build your custom image from a Dockerfile.

For more configuration detail consult the [documentation](https://www.vagrantup.com/docs/docker/configuration.html)


## Building & Running from Vagrant

### Vagrantfile (Pre-Build Docker Image)
```
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.image = "pasing/Centos7-SSH:centos7"
    d.has_ssh = true
  end
end
```

### Vagrantfile (Custom Build Docker Image)
```
ENV['VAGRANT_DEFAULT_PROVIDER'] = 'docker'

Vagrant.configure("2") do |config|
  config.vm.provider "docker" do |d|
    d.build_dir = "."
    d.has_ssh = true
  end
end
```


## Vagrant Usefull Command

### Up

**Command: `vagrant up [name|id]`**
This command creates and configures guest machines according to your Vagrantfile.

### Halt

**Command: `vagrant halt [name|id]`**
This command shuts down the running machine Vagrant is managing.

### Status

**Command: `vagrant status [name|id]`**
This will tell you the state of the machines Vagrant is managing.

### SSH

**Command: `vagrant ssh [name|id] [-- extra_ssh_args]`**

This will SSH into a running Vagrant machine and give you access to a shell.

### Destroy

**Command: `vagrant destroy [name|id]`**
This command stops the running machine Vagrant is managing and destroys all resources that were created during the machine creation process. 


For more command visit [Vagrant CLI](https://www.vagrantup.com/docs/cli/)






