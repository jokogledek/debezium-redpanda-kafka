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