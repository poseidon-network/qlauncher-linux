<h1 align="center">QLauncher on Linux</h1>

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
