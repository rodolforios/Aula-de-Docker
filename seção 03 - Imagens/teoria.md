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

# Camadas das imagens #

* As imagens do Docker são divididas em **camadas** (layers);​

* Cada instrução no Dockerfile **representa uma layer**;​

* Quando algo é atualizado **apenas as layers depois da linha atualizada são refeitas**;​

* O resto permanece em cache, tornando o **build mais rápido**;​

# Download de imagens #

* Podemos **fazer o download de alguma imagem** do hub e deixá-la disponível em nosso ambiente;​

* Vamos utilizar o comando **docker pull < imagem>**;​

* Desta maneira, caso se use em outro container, **a imagem já estará pronta para ser utilizada**;​


# Aprender mais sobre os comandos #

* Todo comando no docker tem acesso a uma **flag --help**;​

* Utilizando desta maneira, **podemos ver todas as opções disponíveis nos comandos**;​

* Para relembrar algo ou executar uma tarefa diferente com o mesmo;​

* Ex:
 ```
 docker run --help;​
 ```

# Múltiplas aplicações, mesmo container #

* Podemos inicializar **vários containers com a mesma imagem**;​

* As aplicações funcionarão em paralelo;​

* Para testar isso, podemos determinar uma **porta diferente** para cada uma, e rodar no **modo detached**;​

# Alterando o nome da imagem e tag #

* Podemos **nomear a imagem** que criamos;​

* Vamos utilizar o comando **docker tag < nome>** para isso;​

* Também podemos **modificar a tag**, que seria como uma versão da imagem, semelhante ao git;​

* Para inserir a tag utilizamos: **docker tag < nome>:< tag>​**

# Iniciando imagem com um nome #

* Podemos **nomear a imagem já na sua criação**;​

* Vamos utilizar a **flag -t**;​

* É possível inserir o nome e a tag, na sintaxe: nome:tag​

* Isso torna o processo de nomeação mais simples;​

Ex: 
```
docker build -t meunode_diferente:minhatag_diferente .
```

# Comando start interativo #

* A **flag -i** pode ser utilizada com o comando start também;​

* Ou seja, não precisamos criar um novo container para utilizá-lo no terminal;​

* O comando é: **docker start -it < container>**

​
Ex:
``` 
docker start -it epic_vaughan
```

# Removendo imagens #

* Assim como nos containers, **podemos remover imagens com um comando**;​

* Ele é o: **docker rmi <  imagem>​**

* Imagens que estão sendo utilizadas por um container, apresentarão um erro no terminal;​

* Podemos utilizar a **flag -f** para forçar a remoção;​

Ex:
```
docker rmi -f  26d80cd96d69
```
# Removendo imagens e containers #

* Com o comando **docker system prune**;​

* Podemos **remover imagens, containers e networks** não utilizados;​

* O sistema irá exigir uma confirmação para realizar a remoção;​

Ex:
```
docker system prune
```
# Removendo container após utilizar​ #

* Um container pode ser automaticamente deletado após sua utilização;​

* Para isso vamos utilizar a **flag --rm**;​

* O comando seria: **docker run --rm < container>**;​

* Desta maneira **economizamos espaço no computador** e deixamos o ambiente mais organizado;​

Ex:
```
docker run --rm -d -p 3000:3000 d6c061121c3f
```
# Copiando arquivos entre containers #

* Para cópia de arquivos entre containers utilizamos o comando: **docker cp​**

* Pode ser utilizado para copiar um arquivo de um diretório para um container;​

* Ou de um container para um diretório determinado;

Ex:
```
docker elated_lovelace:/app/app.js ./copia/
```

# Verificar informações de processamento #

* Para verificar dados de execução de um container utilizamos: **docker top < container>​**

* Desta maneira temos acesso a quando ele foi iniciado, id do processo, descrição do comando CMD;​

Ex:
```
docker top elated_lovelace
```
# Verificar dados de um container #

* Para verificar diversas informações como: **id, data de criação, imagem e muito mais**;​

* Utilizamos o comando **docker inspect &lt;container&gt;**

* Desta maneira conseguimos entender como o container está configurado;​

Ex:
```
docker inspect elated_lovelace
```
# Verificar processamento #

* Para verificar os processos que estão sendo executados em um container, utilizamos o comando: **docker stats**​

* Desta maneira temos acesso ao andamento do processamento e memória gasta pelo mesmo;​

Ex:
```
docker stats elated_lovelace
```
# Autenticação no Docker Hub #

* Para concluir esta aula vamos precisar criar uma conta no: https://hub.docker.com​

* Para autenticar-se pelo terminal vamos utilizar o comando **docker login**;​

* E então inserir usuário e senha;​

* Agora podemos **enviar nossas próprias imagens** para o HUB! =&rpar;

# Logout do Docker Hub #

* Para remover a conexão entre nossa máquina e o Docker Hub, vamos utilizar o comando **docker logout**;​

* Agora não podemos mais enviar imagens, pois não estamos autenticados

# Enviando imagem para o Docker Hub #

* Para enviar uma imagem nossa ao Docker Hub utilizamos o comando **docker push &lt;imagem>**;​

* Porém antes vamos precisar **criar o repositório** para a mesma no site do Hub;​

* Também será necessário **estar autenticado**;​


# Enviando atualização de imagem
* Para enviar uma atualização **vamos primeiramente fazer o build**;
* **Trocando a tag da imagem** para a versão atualizada;
* **Depois vamos fazer um push** novamente para o repositório;
* Assim todas as versões estarão disponíveis para serem utilizadas;