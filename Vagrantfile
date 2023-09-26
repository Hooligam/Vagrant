#Declarando qual Box (imagem), sera utilizada.
Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/bionic64"
  
#Definindo hostname para a maquina virtual.
  config.vm.hostname = "Avanger-Hulk"

#Definindo recursos e configurações.
  config.vm.provider "virtualbox" do |virtual|
    virtual.name = "Avangers"
    virtual.memory = 1024
    virtual.cpus = 2
  end

#Configuração de networking.
#Forwarded Port(Encaminhamento de porta).
config.vm.network "forwarded_port", guest: 80, host: 8090

#Definindo um IP publico.
config.vm.network "public_network", ip: "179.189.41.141"

#Automações(scripts).
config.vm.provision "shell", path: "scripts/atualizar-pacotes.sh"
config.vm.provision "shell", path: "scripts/instalacao-nginx.sh"

end
