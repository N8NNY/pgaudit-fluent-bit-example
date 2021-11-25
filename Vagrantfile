pub_key = ENV["VAGRANT_PUB_KEY"]
bridge_if = ENV["VAGRANT_BRIDGE_IF"]
Vagrant.configure("2") do |config|
  config.vm.box = "generic/ubuntu2004"
  config.vm.network "public_network", bridge: '#{bridge_if}', dev: '#{bridge_if}'

  config.vm.define "postgres" do |postgres|
    postgres.vm.hostname = "postgres.local"
    postgres.vm.provider :libvirt do |libvirt|
      libvirt.memory = 1024
      libvirt.cpus = 2
    end
  end

  config.vm.provision "shell",
  inline: "sudo apt-get update && sudo apt-get install avahi-daemon avahi-discover avahi-utils libnss-mdns mdns-scan -y"
  config.vm.provision "shell", inline: "echo '#{pub_key}' >> /home/vagrant/.ssh/authorized_keys", privileged: false
end
