Vagrant::Config.run do |all_config|
  all_config.vm.define :riak1 do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.forward_port 8069, 8069
    config.vm.forward_port 8098, 8098
    config.vm.forward_port 8087, 8087
    config.vm.network :hostonly, "33.33.33.10"
    config.vm.provider do |pr|
      pr.memory = 1024
    end
    config.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = "cookbooks"
      chef.roles_path = "roles"
      chef.add_role "riak_node"
      chef.json = { :riak => { :erlang => { :node_name => "riak@33.33.33.10" } } }
    end
  end
  all_config.vm.define :riak2 do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network :hostonly, "33.33.33.11"
    config.vm.provider do |pr|
      pr.memory = 1024
    end
    config.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = "cookbooks"
      chef.roles_path = "roles"
      chef.add_role "riak_node"
      chef.json = { :riak => { :erlang => { :node_name => "riak@33.33.33.11" } } }
    end
  end
  all_config.vm.define :riak3 do |config|
    config.vm.box = "ubuntu/trusty64"
    config.vm.network :hostonly, "33.33.33.12"
    config.vm.provider do |pr|
      pr.memory = 1024
    end
    config.vm.provision :chef_solo do |chef|
      chef.cookbooks_path = "cookbooks"
      chef.roles_path = "roles"
      chef.add_role "riak_node"
      chef.json = { :riak => { :erlang => { :node_name => "riak@33.33.33.12" } } }
    end
  end
end
