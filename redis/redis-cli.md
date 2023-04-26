[Back to Home](../README.md#redis)
# Redis CLI
Redis CLI (Command Line Interface) is a command-line
tool used to interact with Redis, an in-memory key-value
data store. With Redis CLI, you can perform various 
operations such as setting and getting values, 
working with lists, sets, and hashes, publishing 
and subscribing to channels, and more.

Here are some common Redis CLI commands:
- SET key value: Sets a key-value pair in Redis
- GET key: Retrieves the value associated with a key
- DEL key: Deletes a key-value pair from Redis
- INCR key: Increments the value associated with a key
- LPUSH key value: Pushes a value onto the beginning of a list
- RPUSH key value: Pushes a value onto the end of a list
- LLEN key: Returns the length of a list
- SADD key value: Adds a value to a set
- SMEMBERS key: Returns all the members of a set
- HSET key field value: Sets the value of a field in a hash
- HGETALL key: Returns all the fields and values of a hash
- PUBLISH channel message: Publishes a message to a channel
- SUBSCRIBE channel: Subscribes to a channel

To use Redis CLI, you need to have Redis installed 
and running on your system. Once you have Redis running,
you can open a terminal and type "redis-cli" to start
the CLI. From there, you can enter commands and interact 
with Redis.