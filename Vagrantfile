VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "generic/debian9"
  config.vm.network "forwarded_port", guest: 80, host: 12380
  config.vm.provider "libvirt" do |vb|
     vb.memory = 512
     vb.random_hostname = true
  end

  config.vm.provision :ansible do |ansible|
    ansible.playbook = "misp.yaml"
  end
end
