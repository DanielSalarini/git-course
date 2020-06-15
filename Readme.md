# Git Course
Este é um repositorio teste para aprender a usar o Git e Github.

### Status dos Arquivos
**UNTRACKED**: Não foi visto pelo Git  
**UNMODIFIED**: Não teve modificação  
**MODIFIED**: Arquivo modificado e não foi levado para o commit  
**STAGED**: Esta pronto para o commit

### Configuração do usuario
```
git config --global
```

* Configurando nome e email
```
git config --global user.name "Daniel Salarini"  
git config --global user.email "salarini.robotica@gmail.com"
```

* VS Code como editor padrão
```
git config --global core.editor "code --wait" 
```

* Ver as alterações  
```
git config --global -e
```

### Inicializando o Git
```
git init
```

### Comandos basicos

* Status dos Arquivos  
```
git status
```

* Arquivo adicionado para o commit  
```
git add 'Nome do Arquivo'

Exemplo de codigo:
git add file.html

// Adicionar todos os arquivos
git add .
```

* Criar um commit ou Snapshot
```  
git commit -m "Mensagem"
git commit -am "Mensagem"
```

### Historico de commits

* Mostrar Historico
```
git log  
git log --author="Nome"  

// Em forma de "grafico", mostra o historico com os Branch, Merge e Rebase
git log --graph
```

* Mostra em ordem alfabetica quais são os autores, quantos commits fizeram e quais eles foram  
```
git shortlog
```

* Mostra so a quantidade e os autores
```  
git shortlog -sn
```

* Ver a alteração de um commit especifico  
```
git show 'CODIGO DO COMMIT'

Exemplo de codigo:
git show f0557a86824147186c0b40f6938313341136be46
```

* Mostrar a modificação antes de adicionar  
```
git diff
```

* Mostrar somente o nome do arquivo modificado  
```
git diff --name-only
```

### Desfazer

* Desfazer a edição  
```
git checkout 'Nome do Arquivo'

Exemplo de codigo:
git checkout Readme.md
```

* Desfazer o arquivo adicionado para o commit  
```
git reset HEAD 'Nome do Arquivo'

Exemplo de codigo:
git reset HEAD file.js
```

* Desfazer commit 

    * Vai excluir o commit e o arquivo vai estar em **STAGED**  
    ```
    git reset --soft 'CODIGO DO COMMIT'
    ```

    * Vai excluir o commit e o arquivo vai estar em **MODIFIED** 
    ```
    git reset --mixed 'CODIGO DO COMMIT'
    ```

    * Vai excluir o commit e toda alteração feita 
    ```
    git reset --hard 'CODIGO DO COMMIT'  
    ```

    **Exemplo**:
    ```
    git reset --mixed f0557a86824147186c0b40f6938313341136be46
    ```

    > **Note**: Sempre pegar o commit anterior ao qual vai desfazer

### SSH key
Usando o protocolo SSH, você pode conectar e autenticar em servidores e serviços remotos. Com as chaves SSH, você pode se conectar ao GitHub sem fornecer seu nome de usuário ou senha a cada visita.

[Link para criar a **SSH key**](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)

### Repositorio remoto

* Adicionar o repositorio
```
git remote add origin 'HTTPS ou SSH do repositorio'
```

* Listar os repositorios
```
git remote
git remote -v
```

* Enviando para o repositorio

    * Primeira vez
    ```
    git push -u <remote> <branch>

    Exemplo de codigo:
    git push -u origin master
    ```

    * Nas proximas vezes
    ```
    git push <remote> <branch>

    Exemplo de codigo:
    git push origin master
    ```

    * Usando repositorio _"origin"_ e o branch atual depois da primeira vez
    ```
    git push
    ```

* Clonando repositorios
```
git clone 'HTTPS ou SSH do repositorio' 'diretorio do arquivo'
```

### Branch

* Criando branch
```
git checkout -b 'Nome do branch'

Exemplo de codigo:
git checkout -b testing
```

* Listar os branch que existe e mostrar em qual esta
```
git branch
```

* Navegando entres os branch
```
git checkout 'Nome do branch'

Exemplo de codigo:
git checkout master
```

* Apagando o branch
```
git branch -D 'Nome do branch'

Exemplo de codigo:
git branch -D testing
```
* Unindo Branches

    * Merge
    ```
    git merge 'Nome do branch'

    Exemplo de codigo:
    git merge branch-merge
    ```

    * Rebase
    ```
    git rebase 'Nome do branch'

    Exemplo de codigo:
    git rebase branch-rebase
    ```

### .gitignore

Um arquivo gitignore especifica arquivos não rastreados intencionalmente que o Git deve ignorar

[Link da Documentação](https://git-scm.com/docs/gitignore)  
[Link dos Templates](https://github.com/github/gitignore)

### Stash

Para alternar entre um branch e outro é necessário fazer o commit das alterações atuais para depois trocar para um outro branch. Se existir a necessidade de realizar a troca sem fazer o commit é possível criar um stash. O Stash como se fosse um branch temporário que contem apenas as alterações ainda não commitadas.
```
git stash
git stash apply
git stash list
git stash clear
```
