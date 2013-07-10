# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant::Config.run do |config|
  config.vm.box = "precise64"
  config.vm.box_url = "http://files.vagrantup.com/precise64.box"

  config.vm.forward_port 80, 8080
  config.vm.forward_port 12201, 12201 
  config.vm.forward_port 12201, 12201, {:protocol => 'udp'}

  config.vm.provision :chef_solo do |chef|
     chef.cookbooks_path = "cookbooks"
     chef.add_recipe "graylog2::server"
     chef.add_recipe "graylog2::web_interface"
     chef.add_recipe "graylog2::apache2"
     
     chef.json.merge!({
       :graylog2 => {
         :web_interface => {
           :listen_port => 80
         }
       }
     })  
  end
end
