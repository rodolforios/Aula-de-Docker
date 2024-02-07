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

# Expor portas #

* Os **containers de docker não tem conexão com nada de fora deles**;​

* Por isso precisamos expor portas, a **flag é a -p** e podemos fazer assim: -p 80:80;​

* Lembrando que a porta que vai primeiro é a que eu quero expor e a segunda a que eu quero receber do container.

* Desta maneira **o container estará acessível na porta 80**;​

* Podemos testar este exemplo com o nginx!
​
# Parando containers #

* Podemos parar um container com o comando **docker stop < id ou nome >**;​

* Desta maneira estaremos liberando recursos que estão sendo gastos pelo mesmo;​

* Podemos verificar os containers rodando com o comando **docker ps**;

# Hack para execução de comandos #

* Podemos utilizar qualquer comando que necessite um id de um container ou imagem com **apenas seus 3 primeiros dígitos**;​

* docker stop a2b;​

* **O Docker é inteligente o suficiente** para entender essa abreviação;​

* E ele tenta ao máximo **criar ids únicos**;​

# Iniciando container #

Aprendemos já a parar um container com o stop, para voltar a rodar um container podemos usar o comando **docker start < id >**;​

Lembre-se que **o run sempre cria um novo container**;​

Então caso seja necessário aproveitar um antigo, opte pelo start;​

# Definindo nome do container #

* Podemos definir um nome do container com a flag **--name**;​
  
* docker run -d -p 80:80 --name nginx_app nginx

* Se não colocamos, **recebemos um nome aleatório**, o que pode ser um problema para uma aplicação profissional;​

* A flag run é inserida junto do **comando run**;​

# Verificando os logs #

* Podemos **verificar o que aconteceu em um container** com o comando logs;​

* Utilizamos da seguinte maneira: **docker logs < id>​**

* As últimas ações realizadas no container, serão **exibidas no terminal**;

# Removendo containers #

* Podemos **remover um container da máquina** que estamos executando o Docker;​

* O comando é **docker rm < id >**;​

* Se o container estiver rodando ainda, podemos utilizar a **flag -f** (force);​
 
* **docker rm < id > -f** 

* O container removido não é mais listado em docker ps -a;​

​