<h1 align="center">QLauncher on Linux</h1>

# What is QLauncher
Poseidon Miners could install **QLauncher** to their IoT devices as nodes of Poseidon Network. After QLauncher installed, when **Service Providers** pay Cryptocurrency for using **QServices**, Poseidon Miners could earn **QQQ tokens** in realtime via **PoD**, which is a mechanism for recording usage and earnings of node resources (such as Bandwidth, CPU, Storage) to Ethereum.

If you'd like to become one of Poseidon Miners, QLauncher is built for you to add your devices as nodes of Poseidon Network.

You can visit [About Poseidon](https://poseidon.network) for more information.

# Linux & Docker versions supported by QLauncher
### Linux
* Ubuntu 18.04.4
* CentOS 8
* RHEL 8

### Docker
* Docker Version 19.03.6


# How QLauncher Works
### Features
* Poseidon k8s cluster : Collect & dispatch device resources (such as Storage, Bandwidth, CPU) through Poseidon k8s cluster
* system analyzer : Analyze resources shared by the device
* life cycle manager : Check if the device works properly
* OTA : Painless update QLauncher

![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/diagram2.1.png?raw=true "QL diagram")


#### qlauncher-linux
```bash
mkdir ~/qlauncher
wget https://github.com/poseidon-network/qlauncher-linux/releases/download/0.2.3.0/app.tar.gz -o app.tar.gz
tar -vxzf app.tar.gz -C ~/qlauncher/
```

#### Start server
```bash
cd ~/qlauncher
sudo ./qlauncher start &
```

#### Stop server
```bash
cd ~/qlauncher
sudo ./qlauncher stop
```
