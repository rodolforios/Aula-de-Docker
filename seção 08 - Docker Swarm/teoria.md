# O que é orquestração de containers? #

* Orquestração é o ato de conseguir *gerenciar e escalar* os containers da nossa aplicação;​

* **Temos um serviço que rege sobre outros serviços**, verificando se os mesmos estão funcionando como deveriam;​

* Desta forma conseguimos garantir uma aplicação saudável e também que esteja sempre disponível;​

* Alguns serviços: **Docker Swarm, Kubernetes e Apache Mesos**;​

# O que é Docker Swarm? #

* Uma ferramenta do Docker para **orquestrar containers**;​

* Podendo **escalar horizontalmente** nossos projetos de maneira simples;​

* O famoso **cluster**!​

* A **facilidade do Swarm** para outros orquestradores é que todos os comandos são muito semelhantes ao do Docker;​

* Toda instalação do Docker já vem com Swarm, **porém desabilitado**;​

# Conceitos fundamentais #

* **Nodes:** é uma instância (máquina) que participa do Swarm;​

* **Manager Node:** Node que gerencia os demais Nodes;​

* **Worker Node:** Nodes que trabalham em função do Manager;​

* **Service:** Um conjunto de Tasks que o Manager Node manda o Work Node executar;​

* **Task:** comandos que são executados nos Nodes;​