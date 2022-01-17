# O que é docker? #

* O **Docker** é um sofware que **reduz a complexidade de setup** de aplicações;

* Onde **configuramos containers**, que são como servidores para rodar nossas aplicações;

* Com facilidade, podemos criar **ambientes independentes** e que funcionam em diversos SO's;

* E ainda deixa os projetos **performáticos**;

# Por quê Docker? #

* O **Docker** proporciona mais velicidade na configuração do ambiente de um dev;

* **Pouco tempo gasto em manutenção,** containers são executados como configurados;
* **Performance** para executar aplicação, mais pergormático que uma VM;

* Nos livra da **Matrix from Hell**;

# Matrix from Hell #

* Se você pesquisar no Google “ **Matrix from Hell** ”, verá muitos artigos sobre como o Docker resolve a matriz do inferno. Então, qual é a matriz do inferno? Simplificando, é o desafio de empacotar qualquer aplicativo, independentemente do idioma/frameworks/dependências, para que ele possa ser executado em qualquer nuvem, independentemente dos sistemas operacionais/hardware/infraestrutura.

* O Docker resolveu a matriz do inferno ao desacoplar o aplicativo do sistema operacional e do hardware subjacentes. Ele fez isso empacotando todas as dependências dentro dos contêineres do Docker, incluindo o sistema operacional. Isso torna os contêineres do Docker “portáteis”, ou seja, eles podem ser executados em qualquer nuvem ou máquina sem os temidos problemas “funciona nesta máquina”. Esta é a maior razão pela qual o Docker é considerado a nova tecnologia mais quente da última década.

# Qual versão utilizar? #

* O **Docker** é dividido em duas versções: **CE x EE**
* CE é a **Community Edition**, edição gratuita, que nos possibilita utilizar o Docker normalmente, é a que vamos optar;
* EE é a **Enterprise Edition**, edição paga, há uma garantia maior das versões que são disponibilidas e você tem suporte do time do Docker;

# Testando o Docker #

* Vamos testar o Docker utilizando uma **imagem real**;​

* Para rodar containers utilizamos o comando **docker run**;​

* Neste comando **podemos passar diversos parâmetros**;​

* Neste exemplo vamos passar apenas o nome da imagem que é **docker/whalesay**​

* Um comando chamado **cowsay** e uma mensagem;​