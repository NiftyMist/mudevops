Vagrant.require_version ">= 1.8.0"

Vagrant.configure(2) do |config|

  config.vm.box = "centos/7"
  config.vm.network "forwarded_port", guest: 80, host: 8080

  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "main.yml"
    ansible.groups = {
      "webservers" => ["web1"]
    }
    limit = "webservers"
  end
end