# -*- mode: ruby -*-
# vi: set ft=ruby :
 
Vagrant.configure("2") do |config|
  config.vm.box = "opscode_centos-6.3_chef-11.2.0"
  config.vm.box_url = "https://opscode-vm.s3.amazonaws.com/vagrant/opscode_centos-6.3_chef-11.2.0.box"
 
  config.vm.hostname = "vagrant-dd"
 
  config.vm.provision :chef_solo do |chef|
    chef.add_recipe "datadog::cassandra"
    chef.add_recipe "datadog::couchdb"
 
    chef.json = {
      :datadog => {
        :api_key => "nah",
        :haproxy => {
          :stats_url => "HOWDY",
          :stats_user => "me!",
          :stats_password => "yeahright",
        },
        :couch => {
          :instances => [
                         {
                           :server => "localhost"
                         }
                        ]
        },
        :cassandra => {
          :instances => [
                         {
                           :host => "localhost",
                           :port => 7199,
                           :instance => "test"
                         }
                        ]
        }
      }
    }
  end
end
