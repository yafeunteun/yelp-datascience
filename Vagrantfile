# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure(2) do |config|
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "ubuntu/trusty64"


  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8888" will access port 8888 on the guest machine.
  config.vm.network "forwarded_port", guest: 8888, host: 8889
  config.vm.provider "virtualbox" do |v|
    v.memory = 4096
    v.cpus = 2
  end
  

  # Run Iptyhon within the image
  # web-based interface at http://localhost:8888/
  # share the folder /vagrant/notebooks (within the VM) with 
  # the folder /home/ds/notebooks within the container 
  config.vm.provision "docker" do |d|
    d.run "dataquestio/python2-starter",
    args: "-p 8888:8888 -v /vagrant/notebooks/:/home/ds/notebooks" #,
    #cmd: "ipython notebook --no-browser"
  end

end
