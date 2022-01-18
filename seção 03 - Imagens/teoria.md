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

# Executando uma imagem #

* Para executar a imagem primeiramente **vamos precisar fazer o build**;​

* O comando é **docker build < diretório da imagem>**;​

* Para ver a lista de imagens digite **docker images**

* Depois vamos utilizar o **docker run < imagem>** para executá-la;​

# Alterando uma imagem #

* Sempre que alterarmos o código de uma imagem **vamos precisar fazer o build novamente**;​

* Para o Docker é como se fosse **uma imagem completamente nova**;​

* Após fazer o build vamos executá-la por o outro id único criada com o docker run;​