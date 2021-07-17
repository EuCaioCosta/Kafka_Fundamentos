# Arquitetura  

## Tópicos  

- Fluxo de registros
- Similar a uma Tabela SQL
- Divididos em Partições 
  - Local onde as mensagens são gravadas
  - Sequência ordenada e imutável de registro
  - Cada registro na partição é atribuído a um id sequencial (offset)
  - Exclusivamnete do registro na partição
- Multi-assinantes 
  - 0,1 ou muitos consumidores acessam os dados gravados

## Brokers Conceitos  

- Corretores 
- Armazenam os tópicos 
- Cluster Kafka é composto por múltiplos corretores (servidores)
  - Ambiente de produção ter no mínimo 3
- Corretor é identificado por um id

## Replicação dos Tópicos 
- 1 corretor líder (Leader)
  - Receber os dados
- 2 corretores de réplic do líder (ISR - in-sync replica)
  - Sincronizar os dados 

# Producers 

## Producers Conceitos

- Produtores 
  - Enviar os dados 
- Publicar dados nos tópicos de sua escolha
- Escolher qual registro atribuir a qual partição dentro do tópico
  - Balancear a carga
  - Chave no registro

## Producers Confirmação de Escrita

- Existem 3 tipos de confirmação de escrita (acks) para o produtor
  - 0 - Sem confirmação de escrita 
  - 1 - Confirmação de escrita no líder (Padrão)
  - All - Confirmação de escrita no líder e nas réplicas (ISR)

# Consumers 

## Consumers Conceitos 

- Consumidores 
  - Receber os dados
- Cada registro publicado em um tópico
  - Entregue aos consumidores dentro de grupo de consumidores 

## Consumers Grupo de Consumidores 

- Se todas as instâncias do consumidor tiverem no mesmo grupo de consumidores 
  - Registros serão balanceados por carga
- Se todas as instâncias do consumidor tiverem em geupos de consumidores diferentes
  - Cada registro será transmitido para todos os processos

# Gerenciar Tópicos - Linha de Comando

## Tópicos Comandos Básicos

- Listar Tópicos  
``` kafka-topics --bootstrap-server localhost:9092 -list ```   
ou  
``` kafka-topics --zookeeper localhost:2181 -list ```  
- Criar Tópicos  
```kafka-topics --bootstrap-server localhost:9092 --topic <nomeTópico> --create \ --partitions 3 --replication-factor 1```
- Descrever Tópico  
``` kafka-topics --bootstrap-server localhost:9092 --topic <nomeTópico> --describe```
- Deletar Tópico  
``` kafka-topics --bootstrap-server localhost:9092 --topic <nomeTópico> --delete ```

# Producer 

## Linha de Comando

### Producer Console

- Enviar dados 
  - ```kafka-console-producer --broker-list localhost:9092 --topic <nomeTópico>```
- Enviar dados para todos reconhecerm (Leader e ISR)  
  - ```kafka-console-producer --broker-list localhost:9092 --topic <nomeTópico> --producer-property acks=all```  

# Consumer Linha de Comando  

## Consumidor Console 

- Receber mensagens em tempo real
  - ```kafka-console-consumer -bootstrap-server localhost:9092 --topic <nomeTópico>```
- Receber mensagens desde a criação do tópico  
  - ```kafka-console-consumer -bootstrap localhost:9092 --topic <nomeTópico> --from-beginning```
- Criar grupo de consumidores  
  - ```kafka-console-consumer -bootstrap-server localhost:9092 --topic <nomeTópico> --group <nomeGrupo>```

## Grupos de Consumidores - Console  

- Listar os grupos  
  - ```kafka-consumer-groups -bootstrap-server localhost:9092 --list```
- Descrever grupo 
  - ```kafka-consumer-groups -bootstrap-server localhost:9092 --describe --group <nomeGrupo>``` 
- Redefinir o deslocamento do mais antigo 
  - ```kafka-consumer-groups -bootstrap-sever localhost:9092 --group <nomeGrupo>\ --reset-offsets --to-earliest --execute --topic <nomeTópico>```
  