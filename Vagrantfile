
# -*- mode: ruby -*-
# vi: set ft=ruby :

# Vagrantfile API/syntax version. Don't touch unless you know what you're doing!
VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

  config.vm.provision :hosts do |provisioner|
  provisioner.autoconfigure = true

  provisioner.add_host '192.168.56.10', ['web1.local.com', 'web1' ]
  provisioner.add_host '192.168.56.11', ['web2.local.com', 'web2' ]
  provisioner.add_host '192.168.56.12', ['web2.local.com', 'web3' ]


end

config.vm.define "web1" do |web1|

    web1.vm.box = "config.vm.box = "p0bailey/centos-6-6-small"
    web1.vm.network :private_network, ip: "192.168.56.12"
    web1.vm.hostname = "web1.local.com"
    web1.ssh.insert_key = false


    web1.vm.provider "virtualbox" do |v|
        v.customize [ "modifyvm", :id, "--cpus", "1" ]
        v.customize [ "modifyvm", :id, "--memory", "1024" ]
        v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
    end

end
#
# config.vm.define "web2" do |web2|
#
#     web2.vm.box = "centos-6-6-small"
#     web2.vm.network :private_network, ip: "192.168.56.14"
#     web2.vm.hostname = "web2.local.com"
#     web2.ssh.insert_key = false
#
#
#     web2.vm.provider "virtualbox" do |v|
#         v.customize [ "modifyvm", :id, "--cpus", "1" ]
#         v.customize [ "modifyvm", :id, "--memory", "1024" ]
# v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
#     end
#
# end
#
#
# config.vm.define "web3" do |web3|
#
#     web3.vm.box = "centos-6-6-small"
#     web3.vm.network :private_network, ip: "192.168.56.16"
#     web3.vm.hostname = "web3.local.com"
#     web3.ssh.insert_key = false
#
#
#     web3.vm.provider "virtualbox" do |v|
#         v.customize [ "modifyvm", :id, "--cpus", "1" ]
#         v.customize [ "modifyvm", :id, "--memory", "1024" ]
# v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
#     end
#
# end
#
# config.vm.define "jenkins" do |jenkins|
#
#     jenkins.vm.box = "centos-6-6-small"
#     jenkins.vm.network :private_network, ip: "192.168.56.20"
#     jenkins.vm.hostname = "jenkins.local.com"
#     jenkins.ssh.insert_key = false
#
#
#     jenkins.vm.provider "virtualbox" do |v|
#         v.customize [ "modifyvm", :id, "--cpus", "1" ]
#         v.customize [ "modifyvm", :id, "--memory", "1024" ]
# v.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
#     end
#
# end

 end
