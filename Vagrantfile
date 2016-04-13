# -*- mode: ruby -*-
# vi: set ft=ruby :
#
Vagrant.configure(2) do |all_config|
  all_config.vm.define :riak1 do |config|
    config.vm.box = 'ubuntu/trusty64'
    config.vm.network :forwarded_port, guest: 8069, host: 8069
    config.vm.network :forwarded_port, guest: 8098, host: 8098
    config.vm.network :forwarded_port, guest: 8087, host: 8087
    config.berkshelf.berksfile_path = './Berksfile'
    config.berkshelf.enabled = true
    config.vm.network :private_network,
                      ip: '33.33.33.10',
                      virtualbox__intnet: 'riak_cluster',
                      auto_config: false
    config.vm.provider :virtualbox do |pr|
      pr.memory = 1024
    end
    config.vm.provision :chef_solo do |chef|
      chef.roles_path = 'roles'
      chef.add_role 'riak_node'
      chef.json = { riak: { erlang: { node_name: 'riak@33.33.33.10' } } }
    end
  end

  all_config.vm.define :riak2 do |config|
    config.vm.box = 'ubuntu/trusty64'
    config.berkshelf.berksfile_path = './Berksfile'
    config.berkshelf.enabled = true
    config.vm.network :private_network,
                      ip: '33.33.33.11',
                      virtualbox__intnet: 'riak_cluster',
                      auto_config: false
    config.vm.provider :virtualbox do |pr|
      pr.memory = 1024
    end
    config.vm.provision :chef_solo do |chef|
      chef.roles_path = 'roles'
      chef.add_role 'riak_node'
      chef.json = { riak: { erlang: { node_name: 'riak@33.33.33.11' } } }
    end
  end

  all_config.vm.define :riak3 do |config|
    config.vm.box = 'ubuntu/trusty64'
    config.berkshelf.berksfile_path = './Berksfile'
    config.berkshelf.enabled = true
    config.vm.network :private_network,
                      ip: '33.33.33.12',
                      virtualbox__intnet: 'riak_cluster',
                      auto_config: false
    config.vm.provider :virtualbox do |pr|
      pr.memory = 1024
    end
    config.vm.provision :chef_solo do |chef|
      chef.roles_path = 'roles'
      chef.add_role 'riak_node'
      chef.json = { riak: { erlang: { node_name: 'riak@33.33.33.12' } } }
    end
  end
end
