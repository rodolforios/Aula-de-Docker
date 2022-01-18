# O que são imagens? #

* Imagens **são originadas de arquivos que programamos** para que o Docker crie uma estrutura que execute determinadas ações em containers;​

* Elas contém informações como: imagens base, diretório base, comandos a serem executados, porta da aplicação e etc;​

* Ao rodar um container baseado na imagem, **as instruções serão executadas em camadas;​**

# Como escolher uma boa imagem #

* Podemos fazer download das imagens em: https://hub.docker.com;​

* Porém **qualquer um pode fazer upload de uma imagem**, isso é um problema;​

* Devemos então nos atentar as **imagens oficiais**;​

* Outro parâmetro interessante é a q**uantidade de downloads** e a **quantidade de stars**;​

# Criando uma imagem​ #

* Para criar uma imagem vamos precisar de um arquivo **Dockerfile** em uma pasta que ficará o projeto;​

* Este arquivo vai precisar de algumas instruções para poder ser executado;​

* **FROM**: imagem base;​

* **WORKDIR**: diretório da aplicação;​

* **EXPOSE**: porta da aplicação;​

* **COPY**: quais arquivos precisam ser copiados;​