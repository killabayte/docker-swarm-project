Vagrant.configure(2) do |config|
  config.vm.define "manager" do |manager|
    manager.vm.box = "ubuntu/trusty64"
    manager.vm.network "private_network", ip: "192.168.0.248"
    manager.vm.hostname = "manager.example.com"
    manager.vm.provision "shell", path: "docker-swarm-demo/docker_install.sh"
  end
  config.vm.define "agent1" do |agent1|
    agent1.vm.box = "ubuntu/trusty64"
    agent1.vm.network "private_network", ip: "192.168.0.247"
    agent1.vm.hostname = "docker-agent1.example.com"
    agent1.vm.provision "shell", path: "docker-swarm-demo/docker_install.sh"
  end
  config.vm.define "agent2" do |agent2|
    agent2.vm.box = "ubuntu/trusty64"
    agent2.vm.network "private_network", ip: "192.168.0.246"
    agent2.vm.hostname = "docker-agent2.example.com"
    agent2.vm.provision "shell", path: "docker-swarm-demo/docker_install.sh"
  end
end
