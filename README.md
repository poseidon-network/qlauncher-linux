<h1 align="center">QLauncher on Linux</h1>

## What is QLauncher
Everyone can install QLauncher on their IoT device to share unused storage capacity and bandwidth to the Poseidon network to earn cryptocurrency income.
If you'd like to become one of Poseidon Miners and earn income through your devices , QLauncher is built for you to join your devices to the nodes of Poseidon Network.

You can visit [About Poseidon](https://poseidon.network) for more information.

## How QLauncher Works
![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/diagram2.1.png?raw=true "QL diagram")
* Poseidon k8s cluster : Collect & dispatch device resources (such as Storage, Bandwidth, CPU) through Poseidon k8s cluster
* system analyzer : Analyze resources shared by the device
* life cycle manager : Check if the device works properly
* OTA : Painless update QLauncher

## Before You Begin
### Hardware Requirements (Recommended)
* One processor core (x86-64bit) dedicated to each node service
* Minimum of 500 GB with no maximum of available space per node
* Minimum of 100 Mbps bandwidth upstream

### System Requirements
**Linux-based**
* Ubuntu (Recommended)
    * 64-bit version of one of these Ubuntu versions (20.04 is preferred)
    * Kernel version > 5

🙅‍♂️ Linux installed as a Docker container is NOT supported

If your device is Raspberry Pi 4, please set up before you installing QLauncher 👉
[Prepare for Raspberry Pi 4](https://github.com/poseidon-network/qlauncher-linux/blob/master/Prepare%20for%20Raspberry%20Pi.md)

### Install Network Tool
To setup a Node, you first must have Docker installed. Install Docker by following the appropriate installation guide for your OS.
* Ubuntu Docker Installation
```
sudo su
apt-get update
apt-get install curl wget net-tools
```

### Port Forwarding
Please configure ports ([Port configuration guide](https://github.com/poseidon-network/qlauncher-linux/blob/master/Port-configuration.md)) from 32440 to 32449 to ensure the containers work well. You can use [port scanner](https://portscanner.standingtech.com) to check if the port is open.

### Uninstall Old Version of QLauncher
If you have installed a version of QLauncher less than 0.2.5.1 on your device, please uninstall it first to avoid installation failure when installing a new version of QLauncher.
```
sudo -i
cd /root/qlauncher/
sudo ./qlauncher.sh stop
cd ..
sudo rm -R qlauncher
```

## Let's start installing QLauncher 
## Step1. Install QLauncher
```
sudo su
curl -sfL https://get.qlauncher.poseidon.network/install.sh | sh -
```
### Step2. Check if QLauncher has been successfully installed
You need to ensure that all the following check items are running normally to be considered as a successful installation: 
* Check Running Status of QLauncher 
```
sudo systemctl status qlauncher
```
If you see the running status of QLauncher is "active (running)",  it means that QLauncher is installed successfully and started to run on your device :

![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/image/QL_status.png)

Then, `ctrl+z` to go to next step.

* Get QLauncher Info
```
sudo /opt/qlauncherV2/qlauncher.sh check
```
![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/image/QL_check.png)

* Check Running Status of Containers
```
/opt/qlauncherV2/qlauncher.sh status
```
![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/image/QL_pods.png)

## If you fail to install QLauncher, you can try to :
### Restart QLauncher
```
sudo systemctl restart qlauncher
```
**Uninstall and install QLauncher again**
Uninstall
```
sudo /opt/qlauncherV2/qlauncher.sh uninstall
sudo rm -R /opt/qlauncherV2/
```

## If you want to temporarily stop QLauncher running :
Stop QLauncher
```
/opt/qlauncherV2/qlauncher.sh stop
```

Start QLauncher
```
/opt/qlauncherV2/qlauncher.sh start
```

## How to get my crypto income as a contribution reward ?
Our miner contribution reward rule will change with each test phase, please join our [miner community](https://lihi1.com/W5LBu) or [check the current test phase](https://lihi1.com/YjWzj) here.



## Need Help?
* [GitHub issues](https://github.com/poseidon-network/qlauncher-linux/issues) for bug reports and feature requests.
* [Join our community](https://lihi1.com/W5LBu) to ask questions, discuss features, and for general discussion.
