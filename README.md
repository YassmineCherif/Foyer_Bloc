# 5SAE1-Foyer-
[Uploading Vagrantfile…]()

![build manuelle](https://github.com/user-attachments/assets/c82c9571-671e-45d2-bf02-08b7b1effb81)
![webhook](https://github.com/user-attachments/assets/5aa422f7-dca6-4d86-8e3a-df7491a035f3)
![test sans mock](https://github.com/user-attachments/assets/df31a66f-eeb0-4d82-a9ad-ee9aecb41c10)
![test mock](https://github.com/user-attachments/assets/b4f228cb-2634-436d-8775-18d2027a2545)
![SonarQube](https://github.com/user-attachments/assets/7c5b53c9-1610-43ab-9801-928c27f6250c)
![jacoco](https://github.com/user-attachments/assets/d0ff3d60-134a-4752-b2f7-8e960c973042)
![nexus pipeline](https://github.com/user-attachments/assets/704b3d93-57b2-40c2-8a01-bb53dce28f1b)
![nexus interface](https://github.com/user-attachments/assets/97fa3925-c62e-48d6-83eb-831199244424)
![Prometheus](https://github.com/user-attachments/assets/5e1b6a8c-5aac-42e2-a227-aa0c07a2b7e7)
![Grafana](https://github.com/user-attachments/assets/7e7e343e-fe7a-4f92-a239-0a0a9a23ed0e)
![DockerHub image](https://github.com/user-attachments/assets/4b72e3ee-c5d4-4e12-a27d-2ed64ec0fe94)






Vagrant file : 

# -- mode: ruby --
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "bento/ubuntu-22.04"

  # Disable automatic box update checking. If you disable this, then
  # boxes will only be checked for updates when the user runs
  # vagrant box outdated. This is not recommended.
  # config.vm.box_check_update = false

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine. In the example below,
  # accessing "localhost:8080" will access port 80 on the guest machine.
  # NOTE: This will enable public access to the opened port

  # Create a forwarded port mapping which allows access to a specific port
  # within the machine from a port on the host machine and only allow access
  # via 127.0.0.1 to disable public access
  # config.vm.network "forwarded_port", guest: 80, host: 8080, host_ip: "127.0.0.1"

  # Create a private network, which allows host-only access to the machine
  # using a specific IP.
   config.vm.network "private_network", ip: "192.168.33.10"


  # Synced folder between the host machine and the guest VM
   config.vm.synced_folder "C:/Users/Yasoulanda/OneDrive/Desktop/Foyer/5SAE1-G3-Foyer", "/home/vagrant/foyer"


  # Create a public network, which generally matched to bridged network.
  # Bridged networks make the machine appear as another physical device on
  # your network.
  # config.vm.network "public_network"

  # Share an additional folder to the guest VM. The first argument is
  # the path on the host to the actual folder. The second argument is
  # the path on the guest to mount the folder. And the optional third
  # argument is a set of non-required options.
  # config.vm.synced_folder "../data", "/vagrant_data"

  # Disable the default share of the current code directory. Doing this
  # provides improved isolation between the vagrant box and your host
  # by making sure your Vagrantfile isn't accessible to the vagrant box.
  # If you use this you may want to enable additional shared subfolders as
  # shown above.
  # config.vm.synced_folder ".", "/vagrant", disabled: true

  # Provider-specific configuration so you can fine-tune various
  # backing providers for Vagrant. These expose provider-specific options.
  # Example for VirtualBox:
  #
   config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
     vb.memory = "8048"
     vb.cpus = "4"
   end
  

  config.vm.provision "shell", inline: <<-SHELL
  sudo apt update
  sudo apt install -y gedit
SHELL


end
