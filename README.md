# 🌊 Formation pratique Kafka - débutant.e.s

Caractéristiques de notre cluster local  
 
- 3 brokers 
- 9 partions
- replication factor 3

## 1. Bien démarrer  
*  Mettre à jour les images : `docker compose pull`
*  Lancer les conteneurs en mode détaché ( comme ça on peut continuer à utiliser le même terminal) :
* `docker compose up -d`
* Créer mon premier topic sur le broker-1
    * `docker exec broker-1 kafka-topics --create --topic mon-premier-topic --bootstrap-server broker-1:29092`

* Vérifier que le topic respecte la configuration décrite dans la dockerfile
  * En ligne de commande : `docker exec broker-1 kafka-topics --describe --topic mon-premier-topic --bootstrap-server broker-1:29092`

  * Avec AKHQ : 
  >     http://localhost:8080/ui/docker-kafka-server/node

### 1.2 Produire ses premiers messages (depuis un terminal - en passant par docker) : 
`docker exec -it broker-1 kafka-console-producer --topic mon-premier-topic --bootstrap-server broker-1:29092`

### 1.3 Consommer ses premiers messages ( depuis un terminal - en passant par docker)
`docker exec -it broker-1 kafka-console-consumer --topic mon-premier-topic --from-beginning --bootstrap-server broker-1:29092`

### 1.4 Jouez depuis les consoles autant que vous le souhaitez 

Ps: les codeworkers peuvent voir les résultats attendus via cette [page](https://codeworks.getoutline.com/s/43c3b9b1-3e10-437e-b67c-67c1357b806a)

## 2. Au delà du terminal  
