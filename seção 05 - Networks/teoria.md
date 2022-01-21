# O que são Networks no Docker? #

* **Uma forma de gerenciar a conexão do Docker** com outras plataformas ou até mesmo entre containers;​

* As redes ou networks são **criadas separadas do containers**, como os volumes;​

* Além disso existem alguns **drivers de rede**, que veremos em seguida;​

* Uma rede deixa muito simples a comunicação entre containers;​



# Tipos de rede (drivers) #


* **Bridge:** o mais comum e default do Docker, utilizado quando containers precisam se conectar (na maioria das vezes optamos por este driver);​

* **host:** permite a conexão entre um container a máquina que está hosteando o Docker;​

* **macvlan:** permite a conexão a um container por um MAC address;​

* **none:** remove todas conexões de rede de um container;​

* **plugins:** permite extensões de terceiros para criar outras redes;​

# Tipos de conexão #

* Os containers costumam ter três principais tipos de comunicação:​

* **Externa:** conexão com uma API de um servidor remoto;​

* **Com o host:** comunicação com a máquina que está executando o Docker;​

* **Entre containers:** comunicação que utiliza o driver bridge e permite a comunicação entre dois ou mais containers;​

# Listando redes​ #

* Podemos verificar todas as redes do nosso ambiente com: **docker network ls;​**

* **Algumas redes já estão criadas**, estas fazem parte da configuração inicial do docker;​

# Criando rede #

* Para criar uma rede vamos utilizar o comando docker **network create &lt;nome>;​**

* Esta rede será do tipo **bridge**, que é o mais utilizado;​

* Podemos criar diversas redes;​

Ex:
```
docker network create minharedeteste
```
Exemplo de macvlan
```
docker network create -d macvlan meumacvlan
```
# Removendo redes #

* Podemos remover redes de forma simples também: **docker network rm &lt;nome>**;​

* Assim **a rede não estará mais disponível** para utilizarmos;​

* Devemos tomar cuidado com containers já conectados;​

Ex:
```
docker network rm minharedeteste
```

# Removendo redes em massa #

* Podemos remover redes de forma simples também: **docker network prune**;​

* Assim **todas as redes não utilizadas** no momento serão removidas;​

* Receberemos uma mensagem de confirmação do Docker antes da ação ser executada;​

# Instalação do Postman​ #

* Vamos criar uma **API** para testar a conexão entre containers;​

* Para isso vamos utilizar o software **Postman**, que é o mais utilizado do mercado para desenvolvimento de APIs;​

* Link: https://www.postman.com/​

# Conexão externa #

* Os containers **podem se conectar livremente ao mundo externo**;​

* Um caso seria: uma API de código aberto;​

* Podemos acessá-la livremente e utilizar seus dados;​

* Vamos testar!​

Para buildar a imagem 
```
docker build -t flaskexterna .
```
Para criar o container
```
docker run -d -p 5000:5000 --name flaskexternocontainer flaskexterna
```

# Conexão com o host #

* Podemos também **conectar um container com o host do Docker;​**

* **Host** é a máquina que está executando o Docker;​

* Como ip de host utilizamos: **host.docker.internal**​

* No caso pode ser a nossa mesmo! =&rpar;

# Conexão entre containers​ #

* Podemos também estabelecer uma **conexão entre containers**;​

* Duas imagens distintas rodando em **containers separados que precisam se conectar para inserir um dado no banco**, por exemplo;​

* Vamos precisar de uma rede **bridge**, para fazer esta conexão;​

* Agora nosso container de flask vai inserir dados em um MySQL que roda pelo Docker também;​