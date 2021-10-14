# Comandos GIT
Criei esse repositório para ajudar em meus estudos e colaborar com outras pessoas que estão começando.


### Comandos Iniciais do usuário:

#### Definir seu nome:
    git config --global user.name "seu nome..."

#### Definir seu e-mail:
    git config --global user.email "seu email..."

#### Definir seu editor:
    git config --global core.editor VScode

#### #Ler as informações cadastradas:
    git config user.name
    git config user.email

#### Lista todas as informações cadastradas:
    git config --list



### Comandos iniciais do repositório
A seguir serão listados os comandos referentes a criação de um repositório local.
Entte na pasta que está seu projeto.

#### Iniciando seu repositório
Será criado uma pasta oculta .git
    git init

#### Verificar status do repositório
    git status

### Adicionar arquivos ao monitoramento do GIT
#### Adicionando um arquivo específico
    git add nome_do_arquivo
#### Adicionando todos os arquivos
    git add -A
#### Fazer o commit
    git commit -m "descritivo_da_alteração..."
#### Fazer commit adicionando os arquivos ao mesmo tempo
    git commit -am "descritivo_da_alteração..."
#### Verificando todos os commit
    git log


### Branchs
#### Verificando os branchs
Serão listados todos os branchs e marcado com um "*" o branch atual 
    git branch
#### Criar um novo branch
    git branch <nome>
#### Trocar de branch
    git checkout <nome_do_branch>
#### renomeando o branch atual
    git branch -M <nome_do_branch>

### Revertendo Commit
Primeiramente fazer um git log e pegar o id do commit para qual quer retornar.
#### voltar com as alterações feitas antes do commit
    git reset --soft <id_commit>
#### voltar com as alterações feitas antes do commit e antes de adicinar os arquivos para monitoramento
    git reset --mixed <id_commit>
#### voltar com as alterações feitas antes do commit e apagar todas as alterações que foram feitas
    git reset --hard <id_commit>

#### Reverter o commit que deu errado. 
No git log ainda aparece esse commit que deu errado, podendo usar ele posteriormente, após correções.
    git revert --no-edit <id_commit_que_deu_errado>

#### Voltar um arquivo específico para antes das alterações. o "HEAD" faz pegar dentro do branch atual.
    git checkout HEAD --<nome_do_arquivo>

### Verificando diferenças
#### Verificando diferenças nos arquivos antes de fazer o commit
    git diff
#### Verificando as diferenças em um arquivo específico
    git diff <nome_do_arquivo>
#### saber apenas os nomes dos arquivos modificados
    git diff --name-only


### gitignore
Quando não quer que alguns arquivos ou pastas sejam monitorados pelo git, preicsa criar um arquivo .gitignore dentro da pasta e incluir os nomes dos arquivos/pastas em cada linha desse arquivo.


### Criar repositório no GitHub
Para conseguir enviar o repositório será necessário configurar a chavve SSH. No site existe um tutorial para configurar e criar essa chave.

Criar um repositório pelo site do Github
Na própria página do repositório que foi criado já aparecem os comandos necessários.

#### adicionar um repositório remoto do repositório local 
    git remote add origin https://.......
#### verificar o repositorio criado
    git remote
#### verificar mais detalhes
    git remote -v

#### enviar conteudos locais para o remoto
Enviando para o repositório criado (origin) a partir da branch (master)
    git push -u origin master

#### Trazer o que tem no repositório remoto (origin) para local (master)
    git pull origin master

#### Remover um branch remoto (master é o nome que se quer apagar)
    git push origin :master
#### remover um branch local
    git branch -D <nome_do_branch>


#### Clonando repositório remoto na pasta atual
    git clone <url_do_projeto_quer_clonar>