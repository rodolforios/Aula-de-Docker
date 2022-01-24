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