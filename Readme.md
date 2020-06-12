# Git Course (Udemy)
Este é um repositorio teste para aprender a usar o Git e Github.

# Status dos Arquivos
UNTRACKED: Não foi visto pelo Git
UNMODIFIED: Não teve modificação
MODIFIED: Arquivo modificado e não foi levado para o commit
STAGED: Esta pronto pro commit

# Configuração do usuario
git config --global

git config --global user.name "Daniel Salarini"
git config --global user.email "salarini.robotica@gmail.com"

// VS Code como editor padrão
git config --global core.editor "code --wait" 

// Ver as alterações
git config --global -e

# Inicializando
git init

# Comandos basicos
// Status dos Arquivos
git status

// Arquivo preparado para o commit
git add

// Criar um Snapshot ou versão
git commit -m "Mensagem"

# Historico de commits
git log
git log --author="Nome"
git log --graph

// Mostra em ordem alfabetica quais são os autores, quantos commits fizeram e quais eles foram
git shortlog

// Mostra so quantidade e os autores
git shortlog -sn

// Ver a alteração de um commit especifico
git show 'CODIGO DO COMMIT'
ex: git show f0557a86824147186c0b40f6938313341136be46

// Mostrar a modificação antes de commit
git diff

// Mostrar somente o nome do arquivo modificado
git diff --name-only

# Desfazer
// Desfazer a edição
git checkout Arquivo.js

// Desfazer o arquivo adicionado para o commit 
git reset HEAD Arquivo.js

// Desfazer commit
// Vai ignorar o commit e o arquivo vai estar em STAGED
git reset --soft 'CODIGO DO COMMIT'

// Vai ignorar o commit e o arquivo vai estar em MODIFIED
git reset --mixed 'CODIGO DO COMMIT'

// Vai ignorar o commit e tudo que foi feito
git reset --hard 'CODIGO DO COMMIT'
ex: git reset --mixed f0557a86824147186c0b40f6938313341136be46

obs: Sempre pegar o commit anterior !!