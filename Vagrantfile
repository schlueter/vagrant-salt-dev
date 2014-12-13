default_box = 'saucy64'
default_box_url = 'http://opscode-vm-bento.s3.amazonaws.com/vagrant/virtualbox/opscode_ubuntu-13.10_chef-provisionerless.box'

Vagrant.configure('2') do |config|

  config.vm.define 'master' do |master|
    # Choose your base box
    master.vm.box_url = default_box_url
    master.vm.box = default_box

    master.vm.host_name = "master"
    master.vm.network :private_network, ip: "192.168.56.102"

    # Use all the defaults:
    master.vm.provision :shell do |shell|
      shell.inline = 'wget -qO- http://bootstrap.saltstack.org | sh -s -- -M'
    end
  end

  config.vm.define 'minion' do |minion|
    # Choose your base box
    minion.vm.box_url = default_box_url
    minion.vm.box = default_box

    minion.vm.host_name = "minion"
    minion.vm.network :private_network, ip: "192.168.56.103"

    # Use all the defaults:
    minion.vm.provision :salt do |salt|
      salt.minion_config = 'salt/minion'
    end
  end
end
