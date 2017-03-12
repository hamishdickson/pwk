# Kafka producers

When using kafka will always create a producer and a consumer

Kafka only guarentees order within a partition

## Producer properties

3 mandatory properties

- `bootstrap.servers`: list of host:port pairs of Kafka brokers

- `key.serializer`: kafka brokers expect byte arrays as key and value messages but can send java objects. So need to specify class with serializer

- `value.serializer`: similarly to `key` above
