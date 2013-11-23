# Projeto LaaS (Libras as an Service)

## Sumary

### [1. Configuração de Ambiente](#configuração-de-ambiente)

[2. Configuração do Módulo Front-End](#configuração-do-módulo-front-end)

[3. Configuração do Módulo Middleware](#configuração-do-módulo-middleware)

[4. Configuração do Módulo Core](#configuração-do-módulo-core)

## Configuração de Ambiente

## Configuração do Módulo Front-End

## Configuração do Módulo Middleware

## Configuração do Módulo Core

Take me to [clonando um repositório](#criando-um-novo-repositório-no-servidor)

## Adicionando uma nova chave pública ao arquivo de chaves autorizadas

Mova sua chave *.pub para qualquer pasta (a home é usada no exemplo abaixo)

	$ cd ~/
	$ cat ./*.pub >> ~/.ssh/authorized_files

O usuário cuja chave foi adicionada agora terá permissão de leitura/escrita nos repositórios.

## Criando um novo repositório no servidor

Os repositórios estão sendo mantidos na home.

	$ cd ~/
	$ mkdir <nome-do-repositorio>.git && <nome-do-repositorio>.git
	$ git --bare init

Como esse é um repositório compartilhado, então preciso dar permissão de escrita ao grupo

	$ cd <nome-do-repositório>.git
	$ sudo chmod -R g+ws *
	$ sudo chgrp -R <nome-do-grupo> *
	$ git config core.sharedRepository true

Agora qualquer usuário cadastrado terá permissão de leitura/escrita ao git através do protocolo SSH

## Clonando um repositório</a>

	$ mkdir new_repository && cd new_repository
	$ git clone lavid@150.165.205.157:<nome-do-repositorio>.git