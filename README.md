# Linux Utils 
### Renomeia arquivos com nome maiúsculo para minúsculo.
```shell
for i in $( ls | grep '[[:upper:]]' ); do mv -i $i `echo $i | tr 'A-Z' 'a-z'`; done
```
### Renomeia arquivos, trocando - por _
```shell
for i in $( ls | grep '-' ); do mv -i $i `echo $i | tr '-' '_'`; done
```
