Vagrant.configure(2) do |config|
  config.vm.box = "ubuntu/trusty64"
  config.vm.network :private_network, ip: "192.168.33.98"
  config.vm.network "forwarded_port", guest: 80, host: 8081
  config.vm.network "forwarded_port", guest: 8001, host: 8001
  # config.vm.network "forwarded_port", guest: 443, host: 443
  
  config.vm.boot_timeout = 120


  config.vm.provision "ansible" do |ansible|
    ansible.playbook = "provisions/playbook.yml"
  end
end
