# File Utils
## Rename
#### Renomeia arquivos com nome maiúsculo para minúsculo.
```shell
for i in $( ls | grep '[[:upper:]]' ); do mv -i $i `echo $i | tr 'A-Z' 'a-z'`; done
```
#### Renomeia arquivos, trocando - por _
```shell
for i in $( ls | grep '-' ); do mv -i $i `echo $i | tr '-' '_'`; done
```
# HTTP Requests
## Faz uma requisicao http, utilizando POST
```shell
data='{"text": "ola alunos!","id": 123}'
url=http://localhost:8080/polling
curl -X POST -H "content-type: application/json" -d $data $url
```
## Faz uma requisicao http, utilizando GET
```shell
url=http://localhost:8080/polling
curl -X GET $url
```
# Kill Proccess
## Encontra todos os processos rodando em uma determinada porta
```shell
lsof -i:<port>
```
## Se quiser matar os processos, pegue o pid da resposta do código anterior e substitua no código abaixo: 
```shell
kill <pid>
```

# Git Utils
## Ctrl + Z in git
### Reverter uma modificação em arquivo específico que ainda não foi added e not pushed
```shell
git checkout -- <file_not_added>
# e.g.: git checkout -- index.html
```
### Reverter uma modificação em arquivo específico que já foi added e not pushed
```shell
git reset HEAD <file_added>
# e.g.: git reset HEAD index.html
```
### Reverter uma modificação em arquivo específico que já foi commited e not pushed
```shell
git revert <hash_of_commit_to_undo>
# e.g.: git revert 7c83b4d
```

## Delete branchs
### Deletar uma branch local
```shell
git branch -d <branch_name>
# e.g.: git branch -d bugfix/1230
```
### Deletar uma branch remota
```shell
git push <remote_alias> --delete <branch_name>
# e.g.: git push origin --delete bugfix/1230
```
# Alias
## [Windows] Como adicionar um alias permanente para o Git Bash
- Para adicionar um alias permanente, edite esse arquivo: **/C/Program Files/Git/etc/profile.d/aliases.sh**
- Abra seu editor como administrador
- Adicione seu alias e salve o arquivo
- Abra o git bash, digite 'alias', e pronto!
```shell
$ alias
alias ls='ls -F --color=auto --show-control-chars'
alias ll='ls -l'
```
## [Mac/Linux] Como adicionar um alias permante para o terminal
- Inicie o terminal
- Digite cd ~/ para ir para o seu diretório home
- Edite .bash_profile com seu editor favorito.
```shell
alias ls='ls -F --color=auto --show-control-chars'
alias ll='ls -l'
``` 
**OBS:** Se o arquivo não existir, crie-o.
- Digite ./.bash_profile para recarregar o terminal.
