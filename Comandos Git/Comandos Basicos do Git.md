# Comandos Básicos do Git 

## Situação

* Modificado (modified);
* Preparado (staging/index)
* Consolidado (comitted);

##### Geral
	git help
	
##### Comando específico
	git help add
	git help commit
	git help <qualquer_comando_git>

## Configuração 

##### Listar configurações
	git config --list

##### Atribuir usuário
	git config --global user.name "Thiago Souza"

##### Atribuir email
	git config --global user.email mctks2@hotmail.com


## Repositório Local

### Criar novo repositório

	git init

### Verificar situação dos arquivos/diretórios

	git status

### Adicionar arquivo/diretório (staging area)

##### Adicionar um arquivo em específico

	git add meu_arquivo.txt

##### Adicionar um diretório em específico

	git add meu_diretorio

##### Adicionar todos os arquivos/diretórios
	
	git add . ou  git *	
		
### Comitar arquivo/diretório

##### Comitar um arquivo
	
	git commit meu_arquivo.txt

##### Comitar vários arquivos

	git commit meu_arquivo.txt meu_arquivo1.txt
	
##### Comitar informando mensagem

	git commit meuarquivo.txt -m "mensagem do commit"

### Remover arquivo/diretório

##### Remover arquivo

	git rm meu_arquivo.txt

##### Remover diretório

	git rm -r diretorio

### Visualizar histórico

##### Exibir histórico
	
	git log
	
##### Exibir resumo do histórico (hash completa, autor, data, comentário e qtde de alterações (+/-))

	git log --stat
	
##### Exibir informações resumidas em uma linha (hash completa e comentário)

	git log --pretty=oneline
	
##### Exibir histórico com formatação específica (hash resumido, autoria, data e comentário)

	git log --pretty=format:"%h - %an, %ar : %s"
	
* %h: Hash Resumido;
* %an: Autoria;
* %ar: Data;
* %s: Comentário.

### Cancelar operações

##### Cancelar alteração local (working directory)
Este comando deve ser utilizando enquanto o arquivo não foi adicionado na **staging area**. 

	git checkout -- meu_arquivo.txt

##### Cancelar alteração local (staging area)
Este comando deve ser utilizando quando o arquivo já foi adicionado na **staged area**.

	git reset HEAD meu_arquivo.txt

Se o resultado abaixo for exibido, o comando reset *não* alterou o diretório de trabalho. 

	Unstaged changes after reset:
	M	meu_arquivo.txt

A alteração do diretório pode ser realizada através do comando abaixo:
	
	git checkout meu_arquivo.txt

## Repositório Remoto

### Exibir os repositórios remotos

	git remote
	
	git remote -v

### Associar repositório local com um repositório remoto

	git remote add origin git@github.com:leocomelli/curso-git.git
	
### Exibir informações dos repositórios remotos

	git remote show origin
	
### Renomear um repositório remoto 

	git remote rename origin curso-git
	
### Desassociar um repositório remoto
	
	git remote rm curso-git

### Enviar arquivos/diretórios para o repositório remoto

O primeiro **push** de um repositório deve conter o nome do repositório remoto e o branch.

	git push -u origin master
	
Os demais **pushes** não precisam dessa informação

	git push

### Atualizar repositório local de acordo com o repositório remoto

##### Atualizar os arquivos no branch atual

	git pull
	
##### Buscar as alterações, mas não aplica-las no branch atual

	git fetch
	
### Clonar um repositório remoto já existente

	git clone git@github.com:leocomelli/curso-git.git
	


