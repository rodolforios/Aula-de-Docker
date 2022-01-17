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

* Vamos executar uma imagem em um container com o comando: docker **run < imagem >**

# Verificar containers executados #

* O comando **docker ps ou docker container ls** exibe quais containers estão sendo executados no momento;​

* Utilizando a **flag -a**, temos também todos os containers já executados na máquina;​

* Este comando é útil para **entender o que está sendo executado e acontece** no nosso ambiente;

# Executar container com interação​ #

* Podemos rodar um container e deixá-lo **executando no terminal**;​

* Vamos utilizar a **flag -it**;​

* Desta maneira **podemos executar comandos disponíveis no container** que estamos utilizando o comando run;​

* Podemos utilizar a imagem do ubuntu para isso!

# Container X VM (Virtual Machine)​ #

* **Container é uma aplicação que serve para um determinado fim**, não possui sistema operacional, seu tamanho é de alguns mbs;​

* VM possui sistema operacional próprio, tamanho de gbs, **pode executar diversas funções ao mesmo** tempo;​

* Containers acabam gastando menos recursos para serem executados, por causa do seu uso específico;​

* VMs gastam mais recursos, porém podem exercer mais funções;​

# Executar container em background​ #

* Quando iniciamos um container que persiste, **ele fica ocupando o terminal**;​

* Podemos executar um container em background, para não precisar ficar com diversas abas de terminal aberto, utilizamos a **flag -d** (detached);​

* Verificamos **containers em background com docker ps** também;​

* Podemos utilizar o nginx para este exemplo!​

​
​