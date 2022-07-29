### Docker Networks: CLI Management
- `docker network ls`
    - show networks
    - network bridge: default Docker virtual network, which is NAT'ed behind the HOST IP
    - network host: it gains performance by skipping virtual networks but sacrificies security of container model
- `docker network inspect <network-name>`
    - inspect the network
- `docker network create my_app_net>`
    - spawns a new virtual network for you to attach containers to 
    - it will also use the 'bridge' driver
    - network driver: built-in or 3rd party extensions that give you virtual network features


### Connect Container to the Network
- `docker container run -d --name new_nginx --network my_app_net nginx`
    - create a container with given network
- `docker network connect <network> <container>`
    - dynamically creates a NIC in a conainer on an existing virtual network
- `docker network disconnect <network> <container>`
    - removes a NIC from a container on a specific virtual network

