# Linux Utils 
### Rename
#### Renomeia arquivos com nome maiúsculo para minúsculo.
```shell
for i in $( ls | grep '[[:upper:]]' ); do mv -i $i `echo $i | tr 'A-Z' 'a-z'`; done
```
#### Renomeia arquivos, trocando - por _
```shell
for i in $( ls | grep '-' ); do mv -i $i `echo $i | tr '-' '_'`; done
```
### Requests HTTP
#### Faz uma requisicao http, utilizando POST
```shell
data='{"text": "ola alunos!","id": 123}'
url=http://localhost:8080/polling
curl -X POST -H "content-type: application/json" -d $data $url
```
#### Faz uma requisicao http, utilizando GET
```shell
url=http://localhost:8080/polling
curl -X GET $url
```
