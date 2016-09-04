Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 9999, host: 9999
  config.vm.network "private_network", ip: "192.168.33.10"

  config.vm.provider "virtualbox" do |vb|
     vb.memory = "2048"
  end

  config.vm.provision "shell", inline: <<-SHELL
      sudo apt-get update
      sudo apt-get -y install default-jdk
      wget 'https://sourceforge.net/projects/bigdata/files/latest/download' -O blazegraph.jar
  SHELL
end
