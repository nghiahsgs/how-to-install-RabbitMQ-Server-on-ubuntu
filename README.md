# how-to-install-RabbitMQ-Server-on-ubuntu
how to install RabbitMQ Server on ubuntu


## Step 1: Install docker
```
http://nghiahsgs.com/cai-dat-va-su-dung-docker-co-ban-tren-ubuntu-server/#comment-1152
```

## Step 2: Pull image
```
docker pull rabbitmq:3-management
```

## Step 3: Start docker image
```
docker run -d -p 15672:15672 -p 5672:5672 --name rabbit-test-for-medium rabbitmq:3-management
```

15672: port of rabbit management
5672: port rabbit mq

## Step 4: Check service is running
```
docker ps
http://your_ip:15672/#/
guest:guest
```
## Step 5: Check service is running
```
HostName: your_ip
UserName: guest
Password: guest
Port: 5672
```
## Step 6: Add connection string to pika
```python
import pika
def create_connection(host,port,username,password):
    credentials = pika.PlainCredentials(username, password)
    parameters  = pika.ConnectionParameters(host=host,port =port,credentials =credentials)
    connection = pika.BlockingConnection(parameters)
    return connection

host = 'ip_vps'
port = 5672
username = 'nghiahsgs4'
password = '261997'
connection = create_connection(host,port,username,password)
```
Note: user and password can create and change in rabbit management
