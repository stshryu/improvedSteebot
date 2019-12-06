Vagrant.configure("2") do |config|

  # Create the target steebot box that will run the code
  config.vm.define "box" do |node|
    node.vm.box="generic/ubuntu1804"
    node.vm.hostname="box"
    node.vm.network :private_network, ip: "192.168.11.101"
    node.vm.synced_folder "../improvedSteebot", "/home/vagrant/vagrant"
    config.vm.provider "virtualbox" do |v|
      v.customize [ "modifyvm", :id, "--uartmode1", "disconnected" ]
    end
  end
end
