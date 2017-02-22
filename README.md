# :book: VM-Node-Dev

Arquivo de configuração do vagrant para criação de Máquina Virtual(VM) com ambiente de desenvolvimento pré-definido para Node.js


## :construction: Pré-requisitos

Para poder montar a Máquina Virtual(VM), é necessário que algumas aplicações estejam instaladas:

* [Git](https://git-scm.com/) - Sistema de controle de versão distribuído (:apple: MacOS - *brew install git*)
* [Vagrant](https://www.vagrantup.com/) - Criar o ambiente (:apple: MacOS - *brew cask install vagrant*)
* [VirtualBox](https://www.virtualbox.org/) - Virtualização da máquina (:apple: MacOS - *brew cask install virtualbox*)


## :computer: Iniciando

##### Uso
Abra o terminal e insira os seguintes comandos:

```
mkdir NewVMNode
cd NewVMNode
git clone git@github.com:ZavaDeveloper/VM-Node-Dev.git
```

##### Iniciando a VM
```
vagrant up
```

Aguarde o proceso de instalação. :coffee:

Logo após o término do processo, a Máquina Virtual será inicializada já com todas as ferramentas já instaladas. :beers:


#### Definição VM

Esse arquivo de configuração contém o sistema operacional :penguin:**Ubuntu 14.04 Desktop**  as seguintas ferramentas de desenvolvimento:

* [Google Chrome](https://www.google.com/chrome/browser/desktop/index.html) - Navegador
* [NVM (Node Version Manager)](https://github.com/creationix/nvm) - Gerenciador de versões do Node.JS
* [NPM (Node Package Manager)](https://www.npmjs.com/) - Gerenciador de Pacotes do Node.JS
* [Node.js (7.5.0)](https://nodejs.org) - plataforma para desenvolvimento server-side utilizando JavaScript
* [PostgreSQL](https://www.postgresql.org/) - Sistema gerenciador de banco de dados objeto relacional
* [MongoDB](https://www.mongodb.com/) - Banco de dados orientado a documentos de alta performance
* [Git]() - Sistema de controle de versão distribuído e sistema de gerenciamento de código fonte
* [Visual Studio Code](https://code.visualstudio.com/) - Editor de código-fonte

![configuracoes](https://lh3.googleusercontent.com/-mC9OFyyFps0/WKYBVbn_VgI/AAAAAAAACpw/h821_F5FIzwrHRSdwChhyyme7PfxWNqqACL0B/h1080/2017-02-16.png)


## :information_source: Alterações da VM

Caso deseje mudar as configurações da máquina, algumas opções podem ser alteradas:

##### Sistema Operacional

Para buscar outras versões de S.O. basta acessar a página do [Atlas](https://atlas.hashicorp.com/boxes/search), escolher a opção mais adequada e alterar o nome do box nas configurações.

```
config.vm.box = "box-cutter/ubuntu1404-desktop"
```

##### Nome da máquina

Basta alterar a seguinte configuração pra mudar o nome padrão da máquina:
```
vb.name = "Ubuntu 1404 - Desenvolvimento"
```

##### Interface Gráfica

Caso deseje desativar as opções gráficas, basta alterar a seguinte configuração pra **False**:


```
vb.gui = true
```

Com isso, para acessar a máquina, basta utiliza o comando

```
vagrant ssh
```

##### Memória e CPU

A quantidade de memória RAM e processadores utilizados pelo sistema operacional podem ser alterados na seguinte configuração:
```
vb.memory = "3072"
```
```
vb.cpus = 1
```

Para mais informações sobre configurações do *vagrantfile*, basta acessar a documentação do [Vagrant](https://www.vagrantup.com/docs/).

## :notebook: Outros Comandos Vagrant CLI

Para utilizar os comandos abaixo, abra o terminal e acesse a pasta aonde se encontra o arquivo *vagrantfile*.

Caso queira desligar a máquina em funcionamento, basta digita o seguinte comando:

```
vagrant halt
```

Para destruir uma máquina que não será mais utilizada:

```
vagrant destroy
```

Para listar e verificar o estado de todas as máquinas criadas, utilize:

```
vagrant global-status
```

Outros comandos podem ser encontrados na documentação do [Vagrant](https://www.vagrantup.com/docs/cli/).

## :heart: Autores

* **Eder** - *Developer* - [@ZavaDev](https://github.com/ZavaDev)
* **Patrick** - *Developer* - [@PatrickZava](https://github.com/PatrickZava)

