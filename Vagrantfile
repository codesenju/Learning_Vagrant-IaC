Vagrant.configure("2") do |config|

  config.vm.define "docker" do |docker|
    docker.vm.provision "shell", "inline": "sudo apt-get update"
    docker.vm.provision "shell", "inline": "curl -fsSL https://get.docker.com -o get-docker.sh"
    docker.vm.provision "shell", "inline": "sudo sh get-docker.sh"
    docker.vm.provision "shell", "inline": "sudo usermod -aG docker $(whoami)"

    config.vm.box = "generic/ubuntu1804"
    config.vm.synced_folder ".", "/opt"
    # Set assigned memory to the vm
    config.vm.provider "hyperv" do |h|
      h.memory = 1028
      h.maxmemory = 1028
   end
  end

end

    