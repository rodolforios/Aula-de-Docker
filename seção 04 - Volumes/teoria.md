# O que são volumes? #

* Uma **forma prática de persistir dados** em aplicações e não depender de containers para isso;​

* **Todo dado criado por um container é salvo nele,** quando o container é removido perdemos os dados;​

* Então precisamos dos volumes para gerenciar os dados e também conseguir **fazer backups** de forma mais simples;​

# Tipos de volumes #

* **Anônimos (anonymous):** Diretórios criados pela flag -v, porém com um nome aleatório;​

* **Nomeados (named)**: São volumes com nomes, podemos nos referir a estes facilmente e saber para que são utilizados no nosso ambiente;​

* **Bind mounts:** Uma forma de salvar dados na nossa máquina, sem o gerenciamento do Docker, informamos um diretório para este fim;​

# O problema da persistência #

* Se criarmos um container com alguma imagem, **todos os arquivos que geramos dentro dele serão do container**;​

* Quando o container for removido, perderemos estes arquivos;​

* Por isso precisamos os **volumes**;​

* Vamos criar um exemplo prático!​