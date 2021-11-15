# Git

# Exemplo: Iniciar um repositorio

~~~bash
git init
git remote add origin https://<NOME_USUARIO>@github.com/<NOME_USUARIO>/<NOME_PROJETO>.git
git config --local user.name "<NOME_USUARIO>"
git config --local user.email "<EMAIL_USUARIO>"
git config --local credential.helper store

git pull origin master # se repositorio ja contiver algo

git add * 
git commit -m "Commit inicial"
git push origin master
~~~


## Alguns comandos

~~~shell
# git config - escopos: 
## --system (para todo o SO)
## --local (para o projeto)
## -- global (variaveis globais)

## git config --global
git config --global --list # lista todas configurações do git 
git config --global user.name "rochamauricio"
git config --global user.password "your password"
git config --global user.email "mauricio.mbr@gmail.com"
git config --global credential.helper store # armazena credenciais, salva a opcao em /home/mauricio/.gitconfig
git config --global core.editor "code --wait" #  vscode como editor padrao, abre e espera
git config --global core.editor "vi"
git config --global -l # lista configuracoes

git remote set-url origin https://<githubtoken>@github.com/<username>/<repositoryname>.git

## git config - reset
git config --global --unset user.name
git config --global --unset user.nickname
git config --global --unset core.editor

## git config --local: tem efeito so no repositorio local
git config --local user.name "usuario"

# Init, clone e remote
git init # inicializa um repositório local dentro de um dir, cria dir .git, cria a branch main ou master 
git clone URLRepositorio # obtem um clone de um projeto que está no github (repositório remoto) na sua máquina. Já baixa como um repositório local 
git remote add origin URLRepositorio # marca para onde serao enviados os arquivos // origin é apenas um apelido convencionado para nao precisarmos digitar todo o tempo https://... 
git remote -v # lista todos repositórios remotos cadastrados

# Status
git status # verifica o status de todos arquivos do repositório 

# Pull
git pull origin master # "puxa" atualiza o nosso repositório local conforme o repositório remoto, usado quando da conflitos 

# Add, rm e restore
git add nameFile # move o nameFile de untracked para staged 
git add * # move todos arquivos de untracked para staged 
git rm nameFile # apos remover nameFile
git restore --staged nameFile # remove o arquivo de staged 

# Commit e push
git commit -m "msg de commit" # integra os arquivos modificados ao repositório local e retorna os arquivos para o estado de unmodified 
git commit # abre editor de texto padrao para escrever commit e corpo 
git push # "empurrar" publica em um servidor remoto os commits feitos localmente. 
git push origin master # "empurra" (push) o código commitado no repositório local para o repositório remoto 


# Branches
git branch # lista todas as branches do repositorio
git branch -m novoNomeBranch # mudar nome branch (estando na branch)
git branch -m nomeAntigo novoNome # mudar nome branch (estando em outra branch)
git branch -d nomeBranch # deleta branch
git branch nova-branch # cria uma branch?
git checkout -b nova-branch # cria uma branch e muda para ela
git checkout master # muda para a branch master - tag head apontará para primeiro commit da branch master
git fetch # obter branches do repositorio remoto

# Realizando o Merge
git checkout main # va para a branch main: 
git merge nova-branch # junta a nova branch com a branch main

# Utilizando o Rebase
git rebase master # usar com cuidado!

# Stash
git stash save "msgContextoStash" # adiciona tudo que esta no staged (index) no stash (caixinha)
git stash # adiciona mensagem padrao para o stash
git stash list # mostra array de stashes salvos com o contexto
git stash pop 1 # estourando o stash para acessar arquivos do index 1
git stash clear # limpa o stash

# Log
git log # mostra log de commits
git log nomeDir # mostra log de commits em arquivos no dir contribuiting
git log nomeArq # mostra log de commits no arquivo readme.md
git log --oneline # historico de commits de forma resumida
git log --graph # mostra de forma "gráfica" o historico de commits
# gitkraken - ferramenta GUI par git

# Reversão de Commits - manipula arquivos - usar no reposit local
git reset HEAD~1 # "move 1 commit para trás", HEAD~2 == move 2 para trás
git reset --soft HEAD~1  # é como reverter o git commit, volta para logo apos o git add 
git reset --mixed HEAD~1 # reverte arquivos para o working dir (antes do git add), default == mixed
git reset hashDoCommit # move head para o commit com hash: hashDoCommit
git reset --soft hashDoCommit # faz o mesmo para um commit especifico
git reset --hard HEAD~1 # cuidado, destroi codigo, apaga arquivo faz como se o commit nao tivesse existido

# Reversão de Commits - manipula commits, sem flags soft mixed e hard - usar no reposit local
git revert HEAD~1 # gera um commit para a reversao, ex: desfaz uma modificação feita num arquivo
git revert hashDoCommit 

# renomear um commit
~~~

## Exemplos

### Criando um repositorio local e um repositorio remoto

~~~shell
### crie um diretório na sua máquina e entre nele

git init # inicia repositorio local

### crie um arquivo chamado teste.md

git add *
git commit -m "inserindo teste.md"

### crie um repositório no github

git remote add origin URLRepositorioRemoto
git push origin master
~~~

### Clonando um repositorio local

~~~shell
### navegue o diretorio do projeto

git clone URLRepositorioRemoto
~~~

### Inserindo arquivos em um repositório remoto compartilhado

~~~shell
# Primeiro acesso

### navegue até o diretorio onde será o meu repositorio local

git clone URLRepositorioRemoto

### realize as modificações nos arquivos aqui 

git add *
git commit -m "Descricao das alteracoes feitas"

git push origin master # so com versao que nao quebre o site

###################

# Segundo acesso em diante

git pull origin master

### realize as modificações nos arquivos

git add *
git commit -m "Descricao das alteracoes feitas"
git push origin master
~~~

### Resolvendo conflitos de merge

- Um colega deu um git push antes de mim num arquivo que eu também editei. Quando eu der um git push haverá um conflito.

~~~shell
git add *
git commit -m "inserindo minhas modificacoes"
git push origin master

### aqui dará o erro de conflito, preciso integrar as mudanças remotas no meu repositório local

git pull origin master 

### git vai detectar os conflitos de merge e os arquivos em conflito. 

### Resolva o conflito manualmente e salvar o arquivo 

git add *
git commit -m "resolvendo o conflito"
git push origin master
~~~

### Branch Main x Branch Master

~~~shell
### crie um diretorio e entra nele

git init # inicia repositorio local

### crie o arquivo-teste.md

git add *
git commit -m "inserindo arquivo-teste.md"
git remote -v # mostra repositorios remotos que o repositorio local está ligado

### cria repositorio remoto no github inserindo o README.md

git remote add origin URL_DO_REPOSITORIO_REMOTO # aponta o repositorio local par ao remoto
git pull origin master

### fornece usuario e senha do github. 

### vai aparecer: "fatal: Couldn't find remote ref master" pois a branch atual se chama main e não master

git pull origin main # com a main funciona
git branch # mostra em qual branch estamos
git push origin master 

### no repositorio remoto teremos 2 branches
~~~

### Trabalhando com branches 

~~~shell
### crie um repositorio remoto no github com o README.md

### crie um diretorio no pc para armazenar repositorio local e navegue ate repositorio local

git clone URLRepositorio

cd dirProjeto
git remote -v # mostra repositorios remotos que o repositorio local está ligado
touch arquivo1.txt
git add *
git commit -m "adiciona arquivo1.txt na branch main"
git push origin main

git checkout -b nova-funcionalidade # -b cria branch, checkout muda para branch
touch arquivo2.txt
git add *
git commit -m "adiciona arquivo2.txt na branch nova-funcionalidade"

git checkout main # volta para a branch main
git checkout nova-funcionalidade # volta para a branch nova-funcionalidade
git push origin nova-funcionalidade # salva modificacoes na branch no repositorio remoto

# juntando as branchs na branch main
git checkout main
git merge nova-funcionalidade # faz merge da branch nova-funcionalidade na branch main
git push origin main
~~~

## Trabalhando com Stash

~~~shell
### cria repositorio local de teste 

### adiciona 4 arq: file1.txt, ... file4.txt

# cria branch e move-se para ela
git checkout -b funcionalidade-grande 

# cria stash - insere no index 0
git stash save "adicionando arquivos iniciando alterações" # adiciona tudo que esta no staged na caixinha, contexto == "..."

git stash list # mostra array de stashes salvos com o contexto

### cria arquio file5.txt - na branch funcionalidade-grande

# cria stash - insere no index 0 e anterior vai para index 1
git stash # adiciona mensagem padrao para o stash

# estourando o stash para acessar arquivos do index 1
git stash pop 1

git stash list # mostra array de stashes

git stash clear # limpa o stash
~~~

## Trabalhando com gitlog

~~~shell
git clone https://github.com/github/docs

cd docs

git log # mostra log de commits
git log contributing # mostra log de commits em arquivos no dir contribuiting
git log README.md # mostra log de commits no arquivo readme.md
git log --oneline # historico de commits de forma resumida
git log --graph

~~~

## Teorias

- Git é um programa versionador de código criado por Linus Torwalds.
- GitHub é um servidor na nuvem que armazena os códigos. Há outros (GitLab, BitBucket, ...).
- Estados de arquivos:
  - untracked: arquivo recém criado
  - tracked:
    - unmodified
    - modified
    - staged: arquivo preparado para realizarmos o commit
- O git add move o arquivo de untracked para staged
- O git commit integra os arquivos modificados ao repositório local e retorna os arquivos para o estado de unmodified
- Repositório remoto: no servidor
- Repositório local: contém todos os arquivos commitados 
- Ambiente de trabalho > staged > Repositório local

- Commits
  - Melhoram a legibilidade do histórico
  - Devem ser amigáveis, legíveis
  - Devem ser atômicos, unidades sólidas
  - Exemplos de boas mensagens de commits:
    - Implementa catálogo de produtos
    - Reformula Menu lateral
    - Conserta erros de gramática
    - Remove estilo do footer
    - Add a feature
    - Modify an existing feature
    - Remove a feature
  - Portugues ou ingles
    - Siga a convençã do time

- Estrutura do commit
  - Assunto/subject: curto e compreensivel, até 50 caracteres, começa com letra maiúscula, não termina com ponto, escrever na forma imperativa (adiciona, modifica, remove)
  - Corpo: adicione detalhes ao commit, quebre a linha com 75 caracteres, identifique sua audiencia, explique tudo (imagine que a pessoa não entende o que está acontecendo no código), use markdown
  - Rodapé: referencia assuntos relacionados

- Commits semânticos - conventional commits
  - semantic versioning: 3.2.7 == Major.Minor.Patch
    - Major == alterações/new features que quebra a compatibilidade
    - Minor ==  alterações/new features que não quebram a compatibilidade
    - Patch == correção de bug

- Issues - no github
  - descrever problemas/questoes/bugs encontrados

- Tag HEAD
  - A tag head aponta para o último commit válido numa branch
  - Uma tag é um nome que atribuímos a um determinado local no tempo.
  - HEAD é uma tag que acompanha um commit especifico e aponta sempre para o ultimo commit de uma branch
- O nome Main vem sendo adotado mais recentemente no lugar de Master.

- Branches:
  - A branch é uma ramificação do código.
  - Não existe commit sem branch.
  - O nome da branch deve ser bem descritivo.

- Stash
  - Stash é uma "caixinha".
  - Funciona como um array
  - Ao criar nova branch podemos deixar a branch principal limpa usando o stash.
  - Mover-se de uma branch para outra sem carregar nada do contexto anterior.
  - Possui a finalidade de ser utilizado de forma temporária.

- Log - Histórico
  - Registro cronológico de commits

- arquivo .gitignore
  - expressoes regulares de arquivos que não queremos versionar
  - ex.: pasta bin e obj no .NET não queremos versionar:

  ~~~shell
  # dotnet
  bin/
  obj/
  ~~~

- GitLab https://gitlab.com/ 
    https://gitlab.com/rochamauricio
  - Simular ao Github 
  - É open source (o Github não é)
  - Organização de repositórios em grupos
  - CI/CD

## Links

- [Git](https://git-scm.com/docs)
- [Ver](https://www.youtube.com/watch?v=BAmvmaKQklQ&list=PLh2Y_pKOa4Uf-cUQOVNGlz_GVHx8QYoE6)
- [Ver](https://www.youtube.com/watch?v=CGTsIz5t0eY)
- [Pet ufrgs](https://petcomputacaoufrgs.github.io/intro-ao-git/)
- [Semantic Versioning](https://semver.org/)
- [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)

## Continua

- Como setar o usuario e a senha para que ele nao peça de novo
- resolver conflitos de uma branch com arquivos que ela tem em comum com a branch main
- Ver projetos grandes (ex.: do proprio github/doc) e ver como os commits são feitos, padrões de escrita
- ver documentação oficial do github
