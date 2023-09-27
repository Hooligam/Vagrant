# Automação de Máquinas Virtuais com Vagrant
![Vagrant](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQkGs4dJxWvfuy4cI1JM2vWB-tdXjoaE1GrlCt7A533UBQQDpkx-dLa769NhO5l5EP-8Q&usqp=CAU)

O objetivo deste projeto é criar uma solução eficiente e automatizada para provisionar, configurar e gerenciar máquinas virtuais usando a ferramenta Vagrant. Isso permitirá que a equipe de operações e desenvolvimento crie ambientes de desenvolvimento, testes e produção de forma rápida, consistente e personalizada.

**Benefícios**: Os benefícios incluem a redução do tempo gasto na criação manual de máquinas virtuais, a eliminação de erros humanos, a padronização dos ambientes de desenvolvimento e a facilidade de manutenção.

## 📌 Principais comandos do Vagrant 

```
vagrant init
```
Função: Inicializa um novo arquivo de configuração Vagrant (Vagrantfile) em um diretório.
```
vagrant up
```
Função: Inicializa e provisiona uma máquina virtual de acordo com as configurações definidas no Vagrantfile.
```
vagrant destroy
```
Função: Remove completamente a máquina virtual e todos os recursos associados a ela.
```
vagrant reload
```
Função: usado para reinicializar a máquina virtual associada ao Vagrantfile atual, aplicando quaisquer alterações feitas ao arquivo de configuração.

## 📦 Documentação
**Estrutura e configurações**
Após aplicar um "vagrant init" é criado o arquivo Vagrantfile, onde inicialmente temos uma estrutura pronta.
```
Vagrant.configure("2") do |config|

  config.vm.box = "hashicorp/bionic64"

end
```
*Vagrant.configure("2") do |config|*: Isso inicia a configuração do Vagrant. O número "2" nas aspas indica a versão da configuração do Vagrant que está sendo usada.

*config.vm.box = "hashicorp/bionic64"*: Esta linha define a caixa (box) "Imagem" que será usada como base para criar a máquina virtual.

```
config.vm.hostname = "Avanger-Hulk"
```
*config.vm.hostname = "Avanger-Hulk"* : Essa linha define qual será o hostname da nossa máquina virtual.

```
config.vm.provider "virtualbox" do |virtual|
    virtual.name = "Avangers"
    virtual.memory = 1024
    virtual.cpus = 2
  end
```
*config.vm.provider "virtualbox" do |virtual|*: Esta linha define o provedor que será utilizado para criar a máquina virtual.

*virtual.name = "seu name"*: Aqui, você está dando um nome à máquina virtual.

*virtual.memory = 1024*: Esta linha configura a quantidade de memória RAM que será alocada para a máquina virtual

*virtual.cpus = 2*: Aqui, você está configurando a quantidade de núcleos de CPU que a máquina virtual terá.

**Redes (Networking)**

```
config.vm.network "forwardade_port", guest:80, host: 8090

```
Basicamente faz um redirecionamento de porta.

```
config.vm.network "public_network"
```
Para criar uma rede pública. Em uma rede pública, sua máquina virtual recebe um endereço IP acessível na rede local.

**Automação (scripts)**
Podemos subir  nossa VM com algumas automações, podemos, por exemplo, construir scripts ".sh" para serem executados, já podendo subir a VM com aplicativos instalados ou demais ações.

```
config.vm.provision "shell", path: "caminhodoseuscript" 
```
Nessa linha definimos que nosso "provision" será shell, logo apos utilizamos "path" para indicar o caminho do script.

⌨️ com ❤️ por [Elias Assunção](https://github.com/Hooligam) 🔥