config.vm.define "rabbit_elb" do |config|
  config.dns.tld = "dev"
  config.vm.hostname = "rabbit"
  config.vm.network "private_network", ip: "192.168.35.120"
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider "vmware_fusion" do |v|
    v.vmx["memsize"] = "128"
    v.vmx["numvcpus"] = "1"
  end

  config.vm.provider "virtualbox" do |v|
    v.memory = 128
    v.cpus = 1
  end

  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "projects/rabbit-test/site.yml"
    ansible.ask_vault_pass = false
  end
end

(1..3).each do |id|
  config.vm.define "rabbit_#{id}" do |config|
    config.dns.tld = "dev"
    config.vm.hostname = "rabbit-#{id}"
    config.vm.network "private_network", ip: "192.168.35.#{120 + id}"
    config.vm.synced_folder ".", "/vagrant", disabled: true

    config.vm.provider "vmware_fusion" do |v|
      v.vmx["memsize"] = "128"
      v.vmx["numvcpus"] = "1"
    end

    config.vm.provider "virtualbox" do |v|
      v.memory = 128
      v.cpus = 1
    end

    config.vm.provision "ansible" do |ansible|
      ansible.playbook = "projects/rabbit-test/site.yml"
      ansible.ask_vault_pass = false
    end
  end
end
