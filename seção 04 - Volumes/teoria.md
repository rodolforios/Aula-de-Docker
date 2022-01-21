# O que são volumes? #

* Uma **forma prática de persistir dados** em aplicações e não depender de containers para isso;​

* **Todo dado criado por um container é salvo nele,** quando o container é removido perdemos os dados;​

* Então precisamos dos volumes para gerenciar os dados e também conseguir **fazer backups** de forma mais simples;​

# Tipos de volumes #

* **Anônimos (anonymous):** Diretórios criados pela flag -v, porém com um nome aleatório;​

* **Nomeados (named)**: São volumes com nomes, podemos nos referir a estes facilmente e saber para que são utilizados no nosso ambiente;​

* **Bind mounts:** Uma forma de salvar dados na nossa máquina, sem o gerenciamento do Docker, informamos um diretório para este fim;​

# O problema da persistência #

* Se criarmos um container com alguma imagem, **todos os arquivos que geramos dentro dele serão do container**;​

* Quando o container for removido, perderemos estes arquivos;​

* Por isso precisamos os **volumes**;​

* Vamos criar um exemplo prático!​

# Volumes anônimos #

* Podemos criar um volume anônimo (**anonymous**) da seguinte maneira: **docker run -v /data​**

* Onde **/data** será o diretório que contém o volume anônimo;​

* E este container estará atrelado ao volume anônimo;​

* Com o comando **docker volume ls**, podemos ver todos os volumes do nosso ambiente;​

```
docker run -d -p 80:80  --name phpmessages --rm -v /data   phpmessages
```

# Volumes nomeados #

* Podemos criar um volume nomeado **(named)** da seguinte maneira: **docker run -v nomedovolume:/data​**

* Agora o volume tem um nome  e pode ser facilmente referenciado;​

* Em **docker volume ls** podemos verificar o container nomeado criado;​

* Da mesma maneira que o anônimo, este volume tem como função armazenar arquivos;​

```
docker run -d -p 80:80  --name phpmessages --rm -v phpvolume:/var/www/html/messages  phpmessages
```

# Bind mounts #


* **Bind mount** também é um volume, porém ele fica em um diretório que nós especificamos;​

* Então não criamos um volume em sim, **apontamos um diretório**;​

* O comando para criar um bind mount é: **docker run /dir/data:/data​**

* Desta maneira o diretório **/dir/data** no nosso computador, será o volume deste container;​
```
docker run -d -p 80:80 --name phpmessage_container -v "C:\Users\rodol\OneDrive\Documentos\GitHub\Aula-de-Docker\seção04-Volumes\messages:/var/www/html/messages" --rm phpmessages
```

# Bind mounts #

* **Bind mount** também é um volume, porém ele fica em um diretório que nós especificamos;​

* Então não criamos um volume em sim, **apontamos um diretório**;​

* O comando para criar um bind mount é: **docker run /dir/data:/data​**

* Desta maneira o diretório **/dir/data** no nosso computador, será o volume deste container;​

# Atualização do projeto com bind mount #

* **Bind mount** não serve apenas para volumes!​

* Podemos utilizar esta técnica para **atualização em tempo real do projeto**;​

* Sem ter que refazer o build a cada atualização do mesmo;​

* Vamos ver na prática!​

# Criar um volume #

* Podemos criar volumes manualmente também;​

* Utilizamos o comando: **docker volume create &lt;nome>;​**

* Desta maneira temos um **named volume** criado, podemos atrelar a algum container na execução do mesmo;​

Ex:
```
docker volume create volumeteste
```
E para mudar o volume basta usar o código:
```
docker run -d -p 80:80 --name phpmessage_container -v volumeteste:/var/www/html/messages --rm phpmessages
``` 

# Listando todos os volumes #

* Com o comando: **docker volume ls** listamos todos todos os volumes;​

* Desta maneira temos acesso aos **anonymous e os named volumes**;​

* Interessante para saber quais volumes estão criados no nosso ambiente;​

# Checar um volume #

* Podemos verificar os detalhes de um volume em específico com o comando: **docker volume inspect nome**;​

* Desta forma temos acesso ao **local em que o volume guarda dados**, nome, escopo e muito mais;​

* O docker salva os dados dos volumes em algum diretório do nosso computador, desta forma podemos saber qual é;​

Ex:
```
docker volume inspect volumeteste
```
# Remover um volume #

* Podemos também remover um volume existente de forma fácil;​

Vamos utilizar o comando **docker volume rm &lt;nome>​**

Observe que **os dados serão removidos todos também**, tome cuidado com este comando;​
Ex:

```
docker volume rm volumeteste
```
# Removendo volumes não utilizados #

* Podemos **remover todos os volumes que não estão sendo utilizados** com apenas um comando;​

* O comando é: **docker volume prune​**

* Semelhante ao prune que remove imagens e containers, visto anteriormente;​

# Volume apenas de leitura #

* Podemos criar um volume que tem **apenas permissão de leitura**, isso é útil em algumas aplicações;​

* Para realizar esta configuração devemos utilizar o comando: **docker run -v volume:/data:ro**​

* Este **:ro** é a abreviação de read only;​



