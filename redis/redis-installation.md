[Back to Home](../README.md)
# Install Redis on macOS
Use Homebrew to install and start Redis on macOS

This guide shows you how to install Redis on macOS
using Homebrew. Homebrew is the easiest way
to install Redis on macOS. If you'd prefer 
to build Redis from the source files on macOS, 
see Installing Redis from Source.

## Prerequisites
First, make sure you have Homebrew installed. From the terminal, run:
```shell
brew --version
```
If this command fails, you'll need to follow
the Homebrew installation instructions.

## Installation
From the terminal, run:
```shell
brew install redis
```
This will install Redis on your system.

## Starting and stopping Redis in the foreground
To test your Redis installation, you can run the **redis-server**
executable from the command line:
```shell
redis-server
```
If successful, you'll see the startup logs for Redis, 
and Redis will be running in the foreground.

To stop Redis, enter **Ctrl-C**.

## Starting and stopping Redis using launchd
As an alternative to running Redis in the foreground, 
you can also use launchd to start the process 
in the background:
```shell
brew services start redis
```

This launches Redis and restarts it at login.
You can check the status of a launchd managed 
Redis by running the following:
```shell
brew services info redis
```

If the service is running, you'll see 
output like the following:
```shell
redis (homebrew.mxcl.redis)
Running: ✔
Loaded: ✔
User: miranda
PID: 67975
```

To stop the service, run:
```shell
brew services stop redis
```

## Connect to Redis
Once Redis is running, you can test it by running **redis-cli**:
```shell
redis-cli
```

This will open the Redis REPL. Try running some commands:
```shell
127.0.0.1:6379> lpush demos redis-macOS-demo
OK
127.0.0.1:6379> rpop demos
"redis-macOS-demo"
```
