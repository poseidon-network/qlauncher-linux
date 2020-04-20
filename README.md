<h1 align="center">QLauncher on Linux</h1>

# What is QLauncher
Poseidon Miners could install **QLauncher** to their IoT devices as nodes of Poseidon Network. After QLauncher installed, when **Service Providers** pay Cryptocurrency for using **QServices**, Poseidon Miners could earn **QQQ tokens** in realtime via **PoD**, which is a mechanism for recording usage and earnings of node resources (such as Bandwidth, CPU, Storage) to Ethereum.

If you'd like to become one of Poseidon Miners, QLauncher is built for you to add your devices as nodes of Poseidon Network.

You can visit [About Poseidon][]for more information.
[About Poseidon]: https//poseidon.network


#### Diagram
![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/diagram2.1.png?raw=true)

## Installation

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
