# Vagrant Salt Dev
A Vagrant environment for developing Salt formulas. It is designed to be able to work anywhere Vagrant does. 

## How it works
The meat of this project is in the [Vagrantfile][1]. If it doesn't exist (it shouldn't if you haven't run `vagrant up` yet), a new key pair is created for the *minion* and automatically added to the *master*. The *minion's* configuration file at `salt/minion` is then applied using Vagrant's built in salt provisioner.


[1]: ./Vagrantfile
