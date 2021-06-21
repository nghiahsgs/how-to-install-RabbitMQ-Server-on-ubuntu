# how-to-install-RabbitMQ-Server-on-ubuntu
how to install RabbitMQ Server on ubuntu


## STEP 1: Install Erlang
```
https://github.com/nghiahsgs/how-to-install-erlang-ubuntu
```

## STEP 2: Add RabbitMQ Repository to Ubuntu
```
sudo apt update && sudo apt install wget -y
sudo apt install apt-transport-https -y
wget -O- https://dl.bintray.com/rabbitmq/Keys/rabbitmq-release-signing-key.asc | sudo apt-key add -
wget -O- https://www.rabbitmq.com/rabbitmq-release-signing-key.asc | sudo apt-key add -
```

```
echo "deb https://dl.bintray.com/rabbitmq-erlang/debian focal erlang-22.x" | sudo tee /etc/apt/sources.list.d/rabbitmq.list
```

## Step 3: Install RabbitMQ Server Ubuntu 20.04
```
sudo apt update
sudo apt install rabbitmq-server
```
## Step 4: Check status RabbitMQ Server
```
systemctl status  rabbitmq-server.service
systemctl is-enabled rabbitmq-server.service
```
enable rabbitmq-server
```
sudo systemctl enable rabbitmq-server
```

## Step 5: Enable the RabbitMQ Management Dashboard
```
sudo rabbitmq-plugins enable rabbitmq_management
sudo ufw allow proto tcp from any to any port 5672,15672
http://[server IP|Hostname]:15672
guest | guest 
```

## ref
```
https://computingforgeeks.com/how-to-install-latest-rabbitmq-server-on-ubuntu-linux/
```
