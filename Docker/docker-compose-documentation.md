# Docker Compose Documentation

Docker compose is a tool to define multi container applicatons. We will use it to implement:

- [CodeProject.AI](https://www.codeproject.com/Articles/5322557/CodeProject-AI-Server-AI-the-easy-way)
- [MySQL Server](https://ubuntu.com/server/docs/databases-mysql)

## Instructions

This repository has the YAML file needed to define this portion of the "data-visualization" test app. To run it, run the following commands.

1. Create a directory for composer files.
    ```
    mkdir -p ~/DockerCompose
    ```
2. Create volumes directories.
    ```
    mkdir -p ~/DockerVolumes/MySQL/config
    mkdir -p ~/DockerVolumes/MySQL/data
    mkdir -p ~/DockerVolumes/codeproject/etc/ai
    mkdir -p ~/DockerVolumes/codeproject/opt/ai
    mkdir -p ~/DockerVolumes/Mosquitto/config
    mkdir -p ~/DockerVolumes/Mosquitto/data
    mkdir -p ~/DockerVolumes/Mosquitto/log
    ```
3. Move the ```compose.yaml``` file in this repository to the DockerCompose directory. This step assumes you cloned this repository via GitHub Desktop and its stored in the default directory: ```~/Documents/GitHub```. For this case, you can run the following command to move said file.

    ```
    cp ~/Documents/GitHub/data-visualization/Docker/compose.yaml ~/DockerCompose/compose.yaml
    ```
    **Note**: Edit the following
    - The user in *mosquitto volumes* absolute path. This is because mosquitto container does not support relative paths.
4. Move the mosquito **.conf** file located in this repository from ```data-visualization/Mosquitto/mosquitto.conf``` to ```~/DockerVolumes/Mosquitto/config```
    ```
    cp ~/Documents/GitHub/data-visualization/Mosquitto/mosquitto.conf ~/DockerVolumes/Mosquitto/config/mosquitto.conf
    ```
    This file ensures basic settings for testing.
5. Set the terminal to the ```compose.yaml``` file with ```cd ~/DockerCompose``` and run the compose file. This will install or update the containers. This will take some time depending on your connection and systen capabilities.
    ```
    sudo docker compose up -d
    ```
    **Note**: This will download around 12GB. Be sure you have the needed disk space.
6. Check the status of your containers with ```sudo docker ps -a```

At this point, CodeProject.AI, mosquitto and MySQL should be running.
![](https://github.com/hugoescalpelo/data-visualization/blob/main/Images/Screenshot%20from%202023-10-15%2014-38-11.png?raw=true)

If GPU configuration was succesfull, the container creation and execution should lool like this.

![](https://github.com/hugoescalpelo/data-visualization/blob/main/Images/Screenshot%20from%202023-10-06%2020-44-59.png?raw=true)

## Test installation

### CodePorjectAI
In a browser, open [localhost:32168](http://localhost:32168/). You should see the CodeProjectAI status local webpage.

![](https://github.com/hugoescalpelo/data-visualization/blob/main/Images/Screenshot%20from%202023-10-06%2002-07-28.png?raw=true)

### Mosquitto

To check if mosquitto is running you need ```net-tools``` installed. Install it with ```sudo apt install net-tools```. Check if mosquitto is running in port 1883 with following command.
```
netstat -an | grep 1883
```

To test a connection you will need two terminal windows. 

In the first, make a subscription to a test topic. For this you will need the mosquitto container ID, get it with ```sudo docker ps -a```
```
sudo docker exec -it [container-id] mosquitto_sub -h localhost -t mosquitto/test
```
In the secont terminal window, publish with following command.
```
sudo docker exec -it [container-id] mosquitto_pub -h localhost -t mosquitto/test -m "Hello Mosquitto"
```

The message "Hello Mosquitto" will appear in the subscription window.

## Troubleshooting

If you were unable to set up the GPU acces for containers or you dont have a nVidia GPU, you can use the alternative YAML file. Then, change the composer launcher for the following.

```
sudo docker compose2 up -d
```