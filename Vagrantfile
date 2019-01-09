Vagrant.configure("2") do |config|
  config.vm.define "master" do |master|
    master.vm.box = "centos/7"
    master.vm.network "private_network", type: "dhcp"
    master.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
    master.vm.provision "shell", path: "master.sh"
  end

  config.vm.define "worker1" do |worker1|
    worker1.vm.box = "centos/7"
    worker1.vm.network "private_network", type: "dhcp"
    worker1.vm.provider "virtualbox" do |vb|
      vb.memory = "2048"
      vb.cpus = 2
    end
    worker1.vm.provision "shell", path: "worker.sh"
  end
end
