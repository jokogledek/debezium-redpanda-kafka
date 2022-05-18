### overview
test debezium postgre integration with redpanda kafka

### decode incoming message
incoming kafka message can be decoded by using avro decoder from redpanda schema registry at `localhost:8081`

```
redpanda schema registry documentation
https://redpanda.com/blog/schema_registry/
```

```
golang library to decode message from schema registry
https://github.com/riferrei/srclient
```
 

### consumer 
```shell
rpk topic consume pg_order.public.sb_order --brokers=0.0.0.0:29092
```

### set connector config
after running docker compose, execute this request to upload connector config to debezium connector
```shell
curl -i -X POST -H "Accept:application/json" -H "Content-Type:application/json" 127.0.0.1:8083/connectors/ --data "@connector/debezium-connector.json"
```

### replace/delete connector
if you want to delete existing connector, so we can set the new one, run this command
```shell
curl -i -X DELETE localhost:8083/connectors/debezium-connector
```