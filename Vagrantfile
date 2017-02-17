VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.define "graphite" do |graphite|
    # graphite.vm.box = "centos-6-4"
    # graphite.vm.box_url = "https://dl.dropboxusercontent.com/s/z85s74gv74m6flo/centos-6-4.box"
    graphite.vm.box = "debian/jessie64"
    # graphite.vm.box = "ubuntu/xenial64"
    graphite.vm.network :private_network, ip: "172.0.0.10"

    graphite.vm.provision "ansible" do |ansible| 
      ansible.playbook = "monitoring.yml"
    end 
  end

  config.vm.provider "virtualbox" do |v|
    v.customize ["modifyvm", :id, "--memory", "1024"]
  end

end
