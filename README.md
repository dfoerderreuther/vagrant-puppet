vagrant-puppet-host-client
==========================

Vagrant configuration for running a simple puppet agent

## Start VMs

	vagrant up
	vagrant ssh

## Create client configuration

	sudo vi /etc/puppet/manifests/init.pp

	class test {
	        file { '/opt/test.txt':
	                owner => root, group => root, mode => 0555, 
	                content => 'Test', 
	        }
	}
	
	node 'puppetagent.local' {
	        include test
	}

## run client configuration

	sudo puppet apply --verbose
