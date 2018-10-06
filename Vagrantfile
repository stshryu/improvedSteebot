Vagrant.configure("2") do |config|

  # Create the target steebot box that will run the code
  config.vm.define "target" do |node|
    node.vm.box="ubuntu/xenial64"
    node.vm.hostname="target"
    node.vm.network :private_network, ip: "192.168.11.101"
    node.vm.synced_folder "../improvedSteebot", "/home/vagrant/vagrant"
    config.vm.provider "virtualbox" do |v|
      v.customize [ "modifyvm", :id, "--uartmode1", "disconnected" ]
    end

  end

  # Create the controller that will set up the steebot box
  config.vm.define "controller" do |controller|
    controller.vm.box="stshryu/steebot_controller"
    controller.vm.hostname="controller"
    controller.vm.network :private_network, ip: "192.168.11.100"
    controller.vm.synced_folder "ansible/", "/home/vagrant/vagrant"
    config.vm.provider "virtualbox" do |v|
      v.customize [ "modifyvm", :id, "--uartmode1", "disconnected" ]
    end
  end

end
