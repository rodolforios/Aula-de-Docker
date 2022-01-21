# O que é o Docker Compose?​ #

* O **Docker Compose** é uma ferramenta para rodar múltiplos containers;​

* Teremos apenas um arquivo de configuração, que orquestra totalmente esta situação;​

* É uma forma de rodar **múltiplos builds e runs** com um comando;​

* Em **projetos maiores** é essencial o uso do Compose;​

​
# Instalando docker compose no Linux​ #

* **Usuários do Linux** ainda não possuem a ferramenta que utilizaremos nesta seção;​

* Vamos seguir as instruções de: https://docs.docker.com/compose/install/​

* O **docker compose** é essencial para atingirmos os nossos objetos no curso;​

# Criando nosso primeiro Compose #

* Primeiramente vamos criar um arquivo chamado docker-compose.yml na raiz do projeto;​

* Este arquivo vai coordenar os containers e imagens, e possui algumas chaves muito utilizadas;​

* **version:** versão do Compose;​

* **services:** Containers/serviços que vão rodar nessa aplicação;​

* **volumes:** Possível adição de volumes;​

# Rodando o Compose #

* Para rodar nossa estrutura em Compose vamos utilizar o comando: **docker compose up**;​

* Isso fará com que as **instruções no arquivo sejam executadas**;​

* Da mesma forma que realizamos os builds e também os runs;​

* Podemos parar o Compose com **ctrl+c** no terminal;​

```
docker-compose up
```

# Compose em background​ #

* O Compose também pode ser executado em modo **detached**;​

* Para isso vamos utilizar a **flag -d** no comando;​

* E então os containers estarão **rodando em background**;​

* Podemos ver sua execução com **docker ps**;​

```
docker-compose up -d
```


# Parando o Compose #

* Podemos parar o Compose que roda em background com: **docker compose down**;​

* Desta maneira o serviço para e temos os containers adicionados no **docker ps -a**;​

# Variáveis de ambiente #

* Podemos definir variáveis de ambiente para o Docker Compose;​

* Para isso vamos definir um arquivo base em **env_file**;​

* As variáveis podem ser chamadas pela sintaxe: **${VARIAVEL}**​

* Esta técnica é útil quando o dado a ser inserido é **sensível/não pode ser compartilhado**, como uma senha;​

# Redes no Compose​ #

* O Compose cria uma **rede básica Bridge** entre os containers da aplicação;​

* Porém podemos isolar as redes com a chave **networks**;​

* Desta maneira podemos conectar apenas os containers que optarmos;​

* E podemos **definir drivers diferentes** também;​


# Vamos incluir o projeto no Compose #

* Agora vamos inserir o nosso projeto da última seção no Compose;​

* Para verificar na prática como fazer uma transferência de **Dockerfiles para Docker Compose**!​

# Vamos incluir o projeto no Compose​ #

* Agora vamos inserir o nosso projeto da última seção no Compose;​

* Para verificar na prática como fazer uma transferência de **Dockerfiles para Docker Compose**!​