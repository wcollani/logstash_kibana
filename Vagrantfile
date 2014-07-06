# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

hosts = {
#"client0" => "192.168.33.13",
#"client1" => "192.168.33.14",
#"client2" => "192.168.33.15",
#"elastic0" => "192.168.33.19",
#"elastic1" => "192.168.33.20",
#"elastic2" => "192.168.33.21",
"kibana0" => "192.168.33.22",
"kibana1" => "192.168.33.23",
"kibana2" => "192.168.33.24",
#"logstash0" => "192.168.33.16",
#"logstash1" => "192.168.33.17",
#"logstash2" => "192.168.33.18",
#"rmq-node0" => "192.168.33.10",
#"rmq-node1" => "192.168.33.11",
#"rmq-node2" => "192.168.33.12",
"kibana" => "192.168.33.25",
}

Vagrant.configure("2") do |config|
  config.hostmanager.enabled = true
  config.hostmanager.manage_host = true
  config.hostmanager.ignore_private_ip = false
  config.hostmanager.include_offline = true
  hosts.each do |name, ip|
    config.vm.define name do |machine|
        machine.vm.box = "berendt/ubuntu-14.04-amd64"
        machine.vm.hostname = "%s" % name
        machine.vm.network :private_network, ip: ip
        #machine.ssh.private_key_path = "~/.ssh/id_rsa"
        #machine.vm.synced_folder ".", "/vagrant", id: "vagrant-root", disabled: true
        machine.vm.provider "virtualbox" do |v|
          v.name = name
          v.memory = 512
	  #v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
        end
#	machine.vm.provision "ansible" do |ansible|
#        	ansible.playbook = "provisioning/playbook.yml"
#    	end

     end
   end
end
