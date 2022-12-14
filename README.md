Ambiente para estudo dos principais frameworks big data em docker.
<br> Esse setup vai criar dockers com os frameworks HDFS, HBase, Hive, Presto, Spark, Jupyter, Hue, Mongodb, Metabase, Nifi, kafka, Mysql e Zookeeper.
<br>  

# BIG DATA

Com o advento da internet, o volume de dados gerados ao redor do mundo cresceu de forma inesperada conforme os anos foram se passando. A utilização em larga escala de dispositivos móveis ampliou ainda mais a quantidade de dados gerados diariamente.

Os métodos tradicionais para armazenamento e processamento de dados em grandes empresas começaram a não ser suficientes, gerando problemas e gastos cada vez maiores para suprir suas necessidades.

Devido a esses acontecimentos, surgiu o conceito de Big Data, uma área do conhecimento que tem como intuito estudar maneiras de tratar, analisar e gerar conhecimento através de grandes conjuntos de dados que não conseguem ser trabalhados em sistemas tradicionais.

Para entender melhor esse conceito, podemos pensar na forma como esse sistema tradicional de armazenamento e processamento de dados é realizado. Perceba que é colocado aqui no presente como “é realizado”, porque os processos de trabalho com o Big Data não excluem a forma de trabalhar no sistema tradicional em grande parte dos casos, uma vez que muitas empresas não necessitam da utilização de ferramentas do Big Data para manipular os dados, e mesmo as grandes empresas utilizam um sistema híbrido. Dessa forma, as duas maneiras de trabalhar com os dados coexistem.

O sistema tradicional utiliza os famosos SGBDs, ou sistemas gerenciais de banco de dados, que guardam informações de forma estruturada, no formato de tabelas, com linhas e colunas. Utilizam máquinas com grande capacidade de armazenamento e processamento. Quando há a necessidade de expandir a capacidade dessas máquinas, é necessário introduzir novos componentes de hardware, para que tenham mais memória e processamento.

Os problemas que começam a aparecer quando se alcança um grande volume de dados usando esse sistema tradicional são relacionados à escalabilidade, disponibilidade e flexibilidade. Como exemplos, podemos mencionar que é muito custoso o aprimoramento dessas máquinas de maneira vertical a cada vez que é necessário realizar um upgrade, corriqueiramente nesse momento o sistema fica indisponível, já que a máquina está em processo de manutenção.

De forma a compreender a definição de Big Data, é necessário introduzir os conceitos dos V’s do Big Data. Inicialmente, a definição era composta por 3 V’s, mas hoje podemos encontrar definições expandidas com 5, 7 ou mais V’s. Os 7 V’s são: volume, variedade, velocidade, valor, veracidade, variabilidade e visualização.



# BIG DATA ECOSYSTEM COM DOCKER

Ambiente para estudo dos principais frameworks big data em docker.
<br> Esse setup vai criar dockers com os frameworks HDFS, HBase, Hive, Presto, Spark, Jupyter, Hue, Mongodb, Metabase, Nifi, kafka, Mysql e Zookeeper.
<br>  

## SETUP
*OBS: Esse passo deve ser realizado apena uma vez. Após o ambiente criado, utilizar o docker-compose para iniciar os containers como mostrado no tópico INICIANDO O AMBIENTE*

#### Criação do diretório docker:
*OBS: A criação do diretório é importante para os mapeamentos necessários*
          
   * No Linux:
      * Criar o diretório na home do usuário
        ex: /home/user/docker

#### Em um terminal/DOS, dentro diretório docker, realizar o clone do projeto no github
          git clone https://github.com/rodrigo-reboucas/docker-bigdata.git
          
## INICIANDO O AMBIENTE
   
### No terminal, no diretorio bigdata_docker, executar o docker-compose
          docker-compose up -d        

### Verificar imagens
          docker image ls

### Verificar containers
          docker container ls

## SOLUCIONANDO PROBLEMAS 

### Parar um containers
         docker stop [nome do container]      

### Parar todos containers
         docker stop $(docker ps -a -q)
  
### Remover um container
         docker rm [nome do container]

### Remover todos containers
         docker rm $(docker ps -a -q)         

### Dados do containers
         docker container inspect [nome do container]

### Iniciar um container
         docker-compose up -d [nome do container]

### Iniciar todos os containers
         docker-compose up -d 

### Acessar log do container
         docker container logs [nome do container] 

## Acesso WebUI dos Frameworks
 
* HDFS *http://localhost:50070*
* Presto *http://localhost:8080*
* Hbase *http://localhost:16010/master-status*
* Mongo Express *http://localhost:8081*
* Kafka Manager *http://localhost:9000*
* Metabase *http://localhost:3000*
* Nifi *http://localhost:9090*
* Jupyter Spark *http://localhost:8889*
* Hue *http://localhost:8888*
* Spark *http://localhost:4040*

## Acesso por shell

   ##### HDFS

          docker exec -it datanode bash

   ##### HBase

          docker exec -it hbase-master bash

   ##### Sqoop

          docker exec -it datanode bash
        
   ##### Kafka

          docker exec -it kafka bash

## Acesso JDBC

   ##### MySQL
          jdbc:mysql://database/employees

   ##### Hive

          jdbc:hive2://hive-server:10000/default

   ##### Presto

          jdbc:presto://presto:8080/hive/default

## Usuários e senhas

   ##### Hue
    Usuário: admin
    Senha: admin

   ##### Metabase
    Usuário: bigdata@class.com
    Senha: bigdata123 

   ##### MySQL
    Usuário: root
    Senha: secret
   
   ##### MongoDB
    Usuário: root
    Senha: root
    Authentication Database: admin

## Imagens   

[Docker Hub](https://hub.docker.com/u/fjardim)

## Documentação Oficial

* https://zookeeper.apache.org/
* https://kafka.apache.org/
* https://nifi.apache.org/
* https://prestodb.io/
* https://spark.apache.org/
* https://www.mongodb.com/
* https://www.metabase.com/
* https://jupyter.org/
* https://hbase.apache.org/
* https://sqoop.apache.org/
* https://hadoop.apache.org/
* https://hive.apache.org/
* https://gethue.com/
* https://github.com/yahoo/CMAK
* https://www.docker.com/

Este repositório é um fork do [fabiogjardim](https://github.com/fabiogjardim/bigdata_docker)
