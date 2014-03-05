
Vagrant::Config.run do |config|

    config.vm.box_url = "http://files.vagrantup.com/precise64.box"
    config.vm.box = "precise64"

    config.vm.host_name = "myhost"
    config.vm.forward_port 80, 8888

    config.vm.provision :shell, path: 'bootstrap.sh'

end

