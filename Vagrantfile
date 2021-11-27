
# Versão da linguagem
Vagrant.configure("2") do |config|

  # Usar o comando vagrant box list para listar boxes locais
  # boxes at https://vagrantcloud.com/search.
  config.vm.box = "hashicorp/bionic64"

  # Para subir a máquina usar o comando vagrant up
  # Para desligar a máquina usar o comando vagrant halt
  # Acessar máquina usar vagrant ssh

  # Disable automatic box update checking. 
  config.vm.box_check_update = true

  # Create a forwarded port mapping which allows access to a specific port
  config.vm.network "forwarded_port", guest: 80, host: 3306

  # Gerenciador de pacote linux apt
  # Atualizar o repositório usar sudo apt install

  config.vm.provider "virtualbox" do |vb|
    vb.name = "mysql"
  #   # Customize the amount of memory on the VM:
    vb.memory = "2048"
    vb.cpus = 2
  end

  # Enable provisioning with a shell script. Additional provisioners such as
  # Ansible, Chef, Docker, Puppet and Salt are also available. 
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update
    apt-get install -y apache2
    apt-get install -y mysql-server
  SHELL
end
