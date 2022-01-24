# O que é Kubernetes? #

* Uma ferramenta de **orquestração de containers**;​

* Permite a criação de **múltiplos containers em diferentes máquinas (nodes)**;​

* Escalando projetos, formando um **cluster**;​

* Gerencia serviços, garantindo que as aplicações sejam executadas **sempre da mesma forma**;​

* Criada pelo **Google**;​

# Conceitos fundamentais​ #

* **Control Plane**: Onde é gerenciado o controle dos processos dos Nodes;​

* **Nodes**: Máquinas que são gerenciadas pelo Control Plane;​

* **Deployment**: A execução de uma imagem/projeto em um Pod;​

* **Pod**: um ou mais containers que estão em um Node;​

* **Services**: Serviços que expõe os Pods ao mundo externo;​

* **kubectl**: Cliente de linha de comando para o Kubernetes;​

​
# Dependências necessárias #

* O Kubernetes pode ser executado de uma maneira simples em nossa máquina;​

* Vamos precisar do client, **kubectl**, que é a maneira de executar o Kubernetes;​

* E também o **Minikube**, uma espécie de simulador de Kubernetes, para não precisarmos de vários computadores/servidores;​

# Kubernetes no Windows​ #

* Primeiramente vamos instalar o gerenciador de pacotes **Chocolatey**;​

* Depois seguiremos a documentação de instalação do **client de Kubernetes**;​

* Devemos também instalar o **Virtualbox** (não é necessário se você tem o Hyper-V ou o Docker instalado);​

* E por fim o **Minikube**;​

* Na próxima aula vamos inicializar o Minikube!​

# Iniciando o Minikube​ #

* Para inicializar o Minikube vamos utilizar o comando: **minikube start --driver=&lt;DRIVER>​**
```
minikube start --driver=docker
``` 

* Onde o driver vai depender de como foi sua instalação das dependências, e por qualquer um deles atingiremos os mesmos resultados!​

* Você pode tentar: **virtualbox, hyperv e docker**​

* Podemos testar o Minikube com: minikube status​
```
minikube status
```

# Parando o Minikube #

* **Obs:** sempre que o computador for reiniciado, deveremos iniciar o Minikube;​

E podemos pará-lo também com o comando: **minikube stop**​

Para iniciar novamente, digite: **minikube start --driver=&lt;DRIVER>​**

# Acessando a dashboard do Kubernetes #

* O Minikube nos disponibiliza uma **dashboard**;​

* Nela podemos ver todo o detalhamento de nosso projeto: **serviços, pods e etc**;​

* Vamos acessar com o comando: **minikube dashboard​**

* Ou para apenas obter a URL: **minikube dashboard --url​**

# Deployment teoria #

* O **Deployment** é uma parte fundamental do Kubernetes;​

* Com ele criamos nosso serviço que vai rodar nos **Pods**;​

* **Definimos uma imagem e um nome**, para posteriormente ser replicado entre os servidores;​

* A partir da criação do deployment teremos containers rodando;​

* Vamos precisar de uma **imagem no Hub do Docker**, para gerar um Deployment;​

# Criar projeto #

* Primeiramente vamos criar um pequeno projeto, novamente em Flask;​

* Buildar a **imagem** do mesmo;​

```
docker build -t rodolforios18/flask-kub-projeto .
``` 
```
docker run -d -p 5000:5000 --name flask-kub --rm rodolforios18/flask-kub-projeto
```

* Enviar a imagem para o **Docker Hub**;​

* E testar rodar em um **container**;​

* Este projeto será utilizado no **Kubernetes**!​

# Criando nosso Deployment #

* Após este mini setup é hora de rodar nosso projeto no **Kubernetes**;​

* Para isso vamos precisar de um **Deployment**, que é onde rodamos os containers das aplicações nos **Pods**;​

```
kubeclt create deployment flask-deployment --image=rodolforios18/flask-kub-projeto
```

* O comando é: **kubectl create deployment <NOME> --image=&lt;IMAGEM>​**

```
kubectl create deployment flask-deployment --image= 
```

* Desta maneira o projeto de Flask estará sendo orquestrado pelo Kubernetes;​

# Checando Deployments #

* Podemos checar se tudo foi criado corretamente, tanto o **Deployment** quanto a recepção do projeto pelo **Pod**;​

* Para verificar o Deployment vamos utilizar: **kubectl get deployments**

```
kubectl get deployments
```

​

* E para receber mais detalhes deles: **kubectl describe deployments**​

* Desta forma conseguimos **saber se o projeto está de fato rodando** e também **o que está rodando nele**;​

​
# Checando Pods #

* Os **Pods** são componentes muito importantes também, onde os containers realmente são executados;​

* Para verificar os Pods utilizamos: **kubectl get pods​**
```
kubectl get pods
```

* E para saber mais detalhes deles: **kubectl describe pods**
```
kubectl describe pods
```
​

* Recebemos **o status dos Pods** que estão ligados e também **informações importantes sobre eles**;​

# Configurações do Kubernetes #

* Podemos também verificar **como o Kubernetes está configurado**;​

* O comando é: **kubectl config view​**
```
kubectl config view​
```

* No nosso caso: vamos receber informações importantes baseadas no **Minikube**, que é por onde o Kubernetes está sendo executado;​

# Services teoria #

* As aplicações do Kubernetes **não tem conexão com o mundo externo**;​

* Por isso precisamos criar um **Service**, que é o que possibilita expor os Pods;​

* Isso acontece pois os **Pods são criados para serem destruídos** e perderem tudo, ou seja, os dados gerados neles também são apagados;​

* Então o **Service é uma entidade separada dos Pods**, que expõe eles a uma rede;​

​