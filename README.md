# qlauncher-linux

## Install qlauncher-linux
```bash
mkdir ~/qlauncher
wget https://github.com/poseidon-network/qlauncher-linux/releases/download/0.2.3.0/app.tar.gz -o app.tar.gz
tar -vxzf app.tar.gz -C ~/qlauncher/
```

## Start server
```bash
cd ~/qlauncher
sudo ./qlauncher start &
```

## Stop server
```bash
cd ~/qlauncher
sudo ./qlauncher stop
```
