# Choose your base box
box = 'saucy64'
box_url = 'http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-13.10_chef-provisionerless.box'

Vagrant.configure('2') do |config|

  config.vm.define 'master' do |master|
    master.vm.box_url = box_url
    master.vm.box = box

    master.vm.host_name = 'master'
    master.vm.network :private_network, ip: '192.168.56.102'

    master.vm.provision :salt do |salt|
      salt.install_master = true
      salt.install_type = 'stable'
    end
  end

  config.vm.define 'minion' do |minion|
    minion.vm.box_url = box_url
    minion.vm.box = box

    minion.vm.host_name = 'minion'
    minion.vm.network :private_network, ip: '192.168.56.103'

    minion.vm.provision :salt do |salt|
      salt.minion_config = 'salt/minion'
    end
  end
end
