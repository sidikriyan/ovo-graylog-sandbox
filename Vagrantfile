Vagrant.require_version ">= 1.7.0"

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.network "forwarded_port", guest: 9000, host: 9000
  config.ssh.insert_key = false
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.limit = "all"
    ansible.playbook = "graylog.yml"
    ansible.inventory_path= "./inventory/hosts"
  end
  config.vm.provider "virtualbox" do |v|
      v.memory = 2048
        v.cpus = 2
  end
end
