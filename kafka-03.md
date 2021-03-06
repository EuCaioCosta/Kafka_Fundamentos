# Control Center Interface

## Control Center 

- Interface gráfica para monitoramento e gerenciamento do Confluent 
  - Monitoramento  
    - Brokers 
    - Tópicos 
    - Grupos de Consumidores
    - Fluxo de dados
  - Gerenciamento 
    - Conectores 
    - Cluster 
    - Tópicos
  - Criação de Alertas 
  - Desenvolvimento em KSQL 

## Interface Gráfica 

- http://localhost:9092/

# Control Center Criação de Tópicos 

## Kafka Criação de Tópicos 

- Confluent Community 
  - Kafka CLI 
    - ```<path-confluent>/bin/kafka-topics --create -bootstrap-server localhost:9092 --replication-factor 1 --partions 1 --topic users```
  - Instalar Kafka Connect Datagen
    - ```<path-to-confluent>/bin/confluent-hub install / --no-prompt confluentinc/kafka-connect-datagen:latest```

## Configurações Tópicos  

- Configuração simples
  - Nome 
  - Partição
- Outras configurações 
  - Availability
  - Cleanup policy
    - Política para limpar
      - Deletar ou Compactar
    - Execução
      - Tempo 
      - Tamanho
    - Message size
      - Tamanho máximo da mensagem

## Configurações Tópicos 

- Disponibiliadade
  - Máxima
    - Fator de replicação -3
    - Mínimo de replicas de sincronização -1
  - Equilibrada 
    - Fator de replicação -3 
    - Mínimo de réplicas de sincronização -2
  - Moderada
    - Fator de replicação -2
    - Mínimo de replicas de sincronização -1
  - Baixa (Não usar em produção)
    - Fator de replicação -1
    - Mínimo de réplicas de sincronização -1 

# KSQL 

## KSQL Conceitos  

- Engine de Streaming SQL do Kafka
- Interface SQL interativa
  - Facilidade de uso
  - Focada para o processamento streaming no Kafka
  - Sem a necessidade de escrever código em Java ou Python
- Escalável
- Tolerante a falhas
- Tempo real 
- Suporta várias operações de streaming
  - Filtragem de dados
  - Transformações 
  - Agregações 

## KSQL Acesso

- Terminal
  - ```docker exec -it ksqldb-cli bash```
  - ```ksql```

## Comandos Básicos

- Visualizar os tópicos  
  - ```list topics```
- Mostrar conteúdo do tópico em tempo real
  - ```print "<nomeTópico>" <propriedades>```  
- Propriedades 

>from beginning   
       interval  
       limit

