## Utilizando o GIT

Documentação do GIT: [https://git-scm.com/docs](https://git-scm.com/docs)

### comandos básicos do git

- `git init` : inicia o git em um diretório

- `git add "file_name"` : adiciona arquivos ao commit, maneira mais fácil de dizer quais arquivos você quer adicionar ou alterar no seu repositorio, possui variações como usar `.` como parâmetro para enviar todos os arquivos do diretório e dos subdiretórios

- `git commit -m “commit message”` : realiza o commit dos arquivos separados para commit, ele requer uma mensagem de commit para conseguirmos saber o que foi alterado de um commit para o outro

- `git push origin branch_name` : Envia arquivos do repositorio local para o repositorio remoto(GitHub)

- `git pull origin branch_name` : recebe arquivos do repositorio remoto no seu repositorio local(usar sempre antes de fazer qualquer modificação no seu projeto afim de ter a versão mais atualizada do projeto), esse comando é uma junção do `git fetch + git merge`

- `git clone repository_name` : baixa todos os arquivos de um repositorio remoto no seu repositorio local(usar quando começar o projeto)

- `git status` : lista os arquivos que estão sendo monitorados(arquivos staged, modified, untracked entre outros)

- `git fetch` : recebe os arquivos do repositorio remoto sem os substitui-los, podemos usar para comparar com os arquivos locais e tambem trazer branches do repositorio remoto para seu repositorio local

- `git merge "branch_name"`  : Atualiza a branch que esta sendo apontada com os arquivos da branch passada por parametro, ou por uma branch remota recebida pelo  `git fetch`, podemos também fazer merge de 2 branches locais

- `git rebase "branch_name"` : Recebe os commits de outra branch na sua branch atual afim de ter todos os commits de ambas as branches intactas em uma só, o resultado seria o mesmo do merge, porem mais organizado e mais perigoso se for feito em repositorios remotos com o uso de mais desenvolvedores

- `git branch “branch_name”` : Comando utilizado para criar uma branch a partir do snapshot da sua branch atual, se você utiliza-lo sem nenhum parametro será retornado uma lista com todos as suas branches

- `git checkout “branch_name”` : Selecionar a branch passada por parametro, quando usamos esse comando o ponteiro `HEAD` começa a apontar para essa branch em especifico, se utilizarmos o `-b` junto, nós iremos criar uma branch e já selecionarmos ela pra uso

- `git log` : Recebe um registro com todos os commits feitos e algumas propriedades sobre eles, esse comando tem variações

- `git restore "filename"` : Restaura arquivos da work tree podendo ser do index ou de outro commit, se utilizarmos ele com o parametro `—staged` para especificar o local de restauração utilizando o indice do arquivo especifico, fazendo a mesma função do `git reset`

- `git reset HEAD~` : Volta a posição do ponteiro HEAD em 1 commit, dependendo do parametro que você passar para ele alterará a area de staging e working(arquivos), seus principais parametros são:
    - `—soft`: Muda o Ponteiro HEAD de lugar
    - `—mixed ou sem parametro`: Muda o Ponteiro HEAD de lugar e altera a area de stage para a da versão atualmente apontada pelo HEAD
    - `—hard`: Muda o Ponteiro HEAD de lugar e altera a area de stage e as alterações no diretorio de working para a da versão atualmente apontada pelo HEAD

- `git config alias.”command_shorthand” “command”` : configura (se quiser configurar globalmente usar `—global`) comandos(podendo colocar varios parametros) com um novo nome(preferencialmente abreviado), é muito util para aumentar a produtividade

- `origin` é uma abreviação dada pro repositorio remoto usado para clona-lo para seu repositorio local
- `HEAD` é o ponteiro que aponta para a branch em que você esta trabalhando no momento

### Merge x Rebase

- Basicamente o **git merge** e o **git rebase** servem para a mesma coisa: **mesclar alterações de duas branches diferentes**.

- O merge, na maioria das vezes, gera um novo commit, o que pode complicar o histórico, mas nunca o reescreve. (é mais seguro)
- Já o rebase deixa o histórico linear e mais simples, mas alguns commits são reescritos, é muito útil para não “sujar” o histórico do repositório (possui mais riscos).
- Cuidado com rebase, você pode ter que forçar a reescrita para enviar as modificações, e com isso outros contribuidores podem ter conflitos quando tentarem enviar seus commits para a "nova" branch reescrita.