# O que são Containers? #

* Um **pacote de código que pode executar uma ação**, por exemplo: rodar uma aplicação de Node.js, PHP, Python e etc;​

* Ou seja, os nossos projetos serão executados dentro dos containers que criarmos/utilizarmos;​

* **Containers utilizam imagens** para poderem ser executados;​

* **Múltiplos containers podem rodar juntos**, exemplo: um para PHP e outro para MySQL;

# Container x Imagem #

* **Imagem e Container** são recursos fundamentais do Docker;​

* Imagem é o **“projeto”** que será executado pelo container, todas as instruções estarão declaradas nela;​

* Container é o **Docker rodando alguma imagem**, consequentemente executando algum código proposto por ela;​

* O fluxo é: programamos uma imagem e a executamos por meio de um container;

# Onde encontrar imagens?​ #

* Vamos encontrar imagens no repositório do Docker: https://hub.docker.com​

* Neste site podemos **verificar quais as imagens existem** da tecnologia que estamos procurando, por exemplo: Node.js;​

* E também **aprender a como utilizá-las**;​

* Vamos executar uma imagem em um container com o comando: docker run <imagem>