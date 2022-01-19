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