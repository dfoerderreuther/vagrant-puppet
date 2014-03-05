vagrant-puppet-host-client
==========================

Vagrant configuration for running a simple puppet agent

## Start VMs

	vagrant up

## Create client configuration

	vagrant ssh
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

	vagrant ssh
	sudo puppet apply --verbose
