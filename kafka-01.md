# Apache Kafka

## Introdução  

O Kafka é uma plataforma de streaming distribuída.  
- Open Source;
- Ela publica e assina streams de registros;
- Fluxo de registros:
  - Processa
    - Tempo real
  - Armazenamento
    - Tolerante a falhas

## História  
Aqui um breve resumo de sua trajetória.

- 2010
  - Originalmente desenvolvido pelo LinkedIn.
    - Necessidade de integração massiva dos dados.
    - Conceito de Kafka surgido com Jay Kreps e sua equipe.
- 2011
  - Liberado como projeto open source.
- 2012
  - Apache Kafka

## Conceitos do Kafka Cluster
- Kafka é desenvolvido em Scala e Java.
- O Kafka é executado como um cluster em um ou mais servidores que podem abranger vários datacenters.
- O cluster Kafka armazena fluxos de *registros* em categorias denominados **tópicos**.
- Cada registro consiste em uma chave, um valor e um registro de data e hora.
- Kafka é um sistema para gerenciamento de fluxos de dados em tempo real, gerados a partir de web sites, aplicações e sensores.

## Principais API Kafka  

- Producer API
  -  Permite que um aplicativo publique um fluxo de registros em um ou mais tópicos do Kafka.
- Consumer API
  - Permite que um aplicativo assine um ou mais tópicos e processe o fluxo de registros produzidos para eles.
- Streams API  
  - Permite que um aplicativo transforme os fluxos de entrada em fluxos de saída.
- Connector API  
  - Permite criar e executar produtores ou consumidores reutilizáveis ​que conectam tópicos do Kafka a aplicativos ou sistemas de dados existentes.

## Introdução Confluent  
- Fundada em 2014 pelos criadores originais do Apache Kafka. 
  - Jay Kreps
- Plataforma de streaming
  - Uso corporativo
  - Infraestrutura de aplicativos e dados
- o Fornece uma plataforma única 
  - Eventos históricos
  - Tempo real

## Confluent

- Facilitar 
  - Construção de pipelines de dados
  - Aplicativos de streaming em tempo real
  - Integração de dados de várias fontes e locais
- Simplificar
  - Conexão de fontes de dados ao Kafka
  - Criação de aplicativos com o Kafka
  - Infraestrutura Kafka 
    - Proteção
    - Monitoramento
    - Gerenciamento


## Confluent CLI  

- Confluent **C**omand **L**ine **I**nterface (CLI)
- Instalar, administrar a plataforma Confluent
- Aplicação para uso de desenvolvimento
  - Não adequado para uso de produção

- Execução 
  - ``` <path-confluent>/bin/confluent <comando> ```
  - Exemplo 
    - ``` <path-confluent>/bin/confluent list ```

## Confluent CLI - Comandos

- Confluent comandos
  - consume <tópico>
  - produce <tópico>  
  - config < conector >
  - load < conector >
  - unload < conector >
  - Version <serviço>
  - help < comando >
  - list
  - start <serviço>
  - status <serviço> 
  - stop <serviço>
  - top <serviço>
  - log <serviço>
  - current

