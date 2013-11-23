# Projeto LaaS (Libras as an Service)

## Sumário

[1. Configuração de Ambiente](#configuração-de-ambiente)

[2. Configuração do Git](#configuração-do-git)

[3. Configuração do Módulo Front-End](#configuração-do-módulo-front-end)

[4. Configuração do Módulo Middleware](#configuração-do-módulo-middleware)

[5. Configuração do Módulo Core](#configuração-do-módulo-core)

## Configuração de Ambiente

#### Instalando `libv8-dev`:

	$ sudo apt-get install libv8-dev

> Local onde as bibliotecas serão instaladas: /usr/lib/libv8.so*

####  Instalando `node.js`:

	$ sudo apt-get update
	$ sudo apt-get install -y python-software-properties python g++ make
	$ sudo add-apt-repository -y ppa:chris-lea/node.js
	$ sudo apt-get update
	$ sudo apt-get install nodejs

####  Instalando `node-gyp`:

	$ sudo npm install -g node-gyp

#### Comandos para criar e compilar um módulo:

	$ node-gyp configure
	$ node-gyp build

## Configuração do Git

#### Adicionando uma nova chave pública ao arquivo de chaves autorizadas

Mova sua chave _*.pub_ para qualquer pasta:

	$ cat <path-da-chave>/*.pub >> ~/.ssh/authorized_files

> O usuário cuja chave foi adicionada agora terá permissão de leitura/escrita nos repositórios.

#### Criando um novo repositório no servidor

Entre no diretório onde os repositórios irão ficar:

	$ cd ~/
	$ mkdir <nome-do-repositorio>.git && cd <nome-do-repositorio>.git
	$ git --bare init

Como esse é um repositório compartilhado, então é necessário dar permissão de escrita ao grupo:

	$ sudo chmod -R g+ws *
	$ sudo chgrp -R <nome-do-grupo> *
	$ git config core.sharedRepository true

> Agora qualquer usuário cadastrado terá permissão de leitura/escrita no git através do protocolo SSH

#### Clonando um repositório:

	$ mkdir _<folder>_ && cd _<folder>_
	$ git clone <nome-do-usuario>@<ip-do-servidor-git>:<nome-do-repositorio>.git

## Configuração do Módulo Front-End

## Configuração do Módulo Middleware

## Configuração do Módulo Core