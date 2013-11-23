# Projeto LaaS (Libras as an Service) - LAViD

## Instalação do **Ambiente**

## Instalação do Módulo **Front-End**

## Instalação do Módulo **Middleware**

## Instalação do Módulo **Core**

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