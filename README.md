# debezium-kafka

```
docker-compose up --build -d
```

Initialize MongoDB replica set and insert some test data:
```
docker-compose exec mongodb bash -c '/usr/local/bin/init-inventory.sh'
```

# Start JDBC sink connector

```
curl -i -X POST -H "Accept:application/json" -H  "Content-Type:application/json" http://localhost:8083/connectors/ -d @jdbc-sink.json
```

# Start Debezium MongoDB CDC connector
```
curl -i -X POST -H "Accept:application/json" -H  "Content-Type:application/json" http://localhost:8083/connectors/ -d @mongodb-source.json
```
