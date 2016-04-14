# Riak Cluster

This is a simple Vagrant config to create a three-way toy cluster for
local testing and development. It has been updated from its forked
ancestors and uses Vagrant config version 2, and load Riak
via Chef with Berkshelf for dependency acquisition.

This implementation has the following dependencies:

* [VirtualBox](https://www.virtualbox.org/)
* [Berkshelf via Chef DK](https://downloads.chef.io/chef-dk/)
* [vagrant-berkshelf](https://github.com/berkshelf/vagrant-berkshelf)

## Instructions

```
git clone https://github.com/craigwaterman/riak-cluster
cd riak-cluster
berks install
vagrant up
```

## Notes

* This will stand up three (3) Ubuntu 14.04 64-bit machines.
* Thanks to all those from whom this is forked.
