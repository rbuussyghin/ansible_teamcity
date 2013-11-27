# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
  config.vm.box = 'ubuntu_precise'
  config.vm.box_url = 'http://cloud-images.ubuntu.com/vagrant/precise/current/precise-server-cloudimg-amd64-vagrant-disk1.box'

  config.vm.define :teamcity_server do |node|
    node.vm.network 'forwarded_port', guest: 8111, host: 8111

    node.vm.provision 'ansible' do |ansible|
      ansible.playbook = 'provisioning/teamcity_server.yml'
      ansible.verbose = 'v'
    end
  end
end
