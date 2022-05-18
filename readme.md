### overview
test debezium postgre integration with redpanda kafka

### consumer 
```shell
rpk topic consume pg_order.public.sb_order --brokers=0.0.0.0:29092
```