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
* 4 processor cores (x86-64bit) dedicated to each node service
* Minimum of 8GB RAM
* Minimum of 1TB with no maximum of available space per node
* Minimum of 40Mbps bandwidth upstream and downstream

### System Requirements
**Linux-based**
* Ubuntu (Recommended)
    * 64-bit version of one of these Ubuntu versions (20.04 Desktop / 20.04 Server is preferred)
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
Please uninstall old version first to avoid installation failure when installing a new version of QLauncher

* For QLauncher less than 0.2.5.1

```
sudo -i
cd /root/qlauncher/
sudo ./qlauncher.sh stop
cd ..
sudo rm -R qlauncher
```

* For qlauncherV2
```
sudo /opt/qlauncherV2/qlauncher.sh uninstall
sudo rm -R /opt/qlauncherV2/
```
* For qlauncherV3
```
sudo /opt/qlauncherV3/qlauncher uninstall
sudo rm -R /opt/qlauncherV3/
```


## Let's start installing QLauncher 
### Step1. Install QLauncher & Set shared storage capacity
```
sudo su
sh -c "$(curl -sfL https://get.qlauncher.poseidon.network/install-v3.sh)"
```
Then, set the storage space you're willing to contribute :

![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/image/QL_shared_v2.png)

>Notice: Repeat installation is not allowed and will received warning message as below, please uninstall first.

![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/image/Repear_installation.png)


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
sudo /opt/qlauncherV3/qlauncher check
```
![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/image/QL_info.png)

* Check Running Status of Containers
```
/opt/qlauncherV3/qlauncher status
```
![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/image/Container_status.png)

### Step3. Get QRcode and add device to QQQ APP
```
/opt/qlauncherV3/qlauncher bind
```
![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/image/Bind_V3.png)

Scan the QRcode to add your QLauncher to the QQQ app.

You can successfully add your device to QQQ app if your QLauncher runs properly. In the app, you will see a device added :

<img src="https://user-images.githubusercontent.com/48922178/122954262-dddf4080-d3b1-11eb-8c44-896f6b2f4b1f.png" width="20%" height="20%">




## If you fail to install QLauncher, you can try to :
**Restart QLauncher**
```
sudo systemctl restart qlauncher
```
**Uninstall QLauncher**

* For QLauncher less than 0.2.5.1

```
sudo -i
cd /root/qlauncher/
sudo ./qlauncher.sh stop
cd ..
sudo rm -R qlauncher
```

* For qlauncherV2
```
sudo /opt/qlauncherV2/qlauncher.sh uninstall
sudo rm -R /opt/qlauncherV2/
```
* For qlauncherV3
```
sudo /opt/qlauncherV3/qlauncher uninstall
sudo rm -R /opt/qlauncherV3/
```
Once uninstalled, go back to install again

## If you want to temporarily stop QLauncher running :
Stop QLauncher
```
/opt/qlauncherV3/qlauncher stop
```
![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/image/Stop_QLauncher.png)

Start QLauncher
```
sudo systemctl restart qlauncher
```
![image](https://github.com/poseidon-network/qlauncher-linux/blob/master/image/Restart_QLauncher.png)

* We recommend Check Running Status of QLauncher again after restart

## How to get my crypto income as a contribution reward ?
Our miner contribution reward rule will change with each test phase, please join our [miner community](https://discord.com/invite/8DzbJG5WVt) or [check the current test phase](https://lihi1.cc/2TMY8) here.



## Need Help?
* [GitHub issues](https://github.com/poseidon-network/qlauncher-linux/issues) for bug reports and feature requests.
* [Join our community](https://discord.com/invite/8DzbJG5WVt) to ask questions, discuss features, and for general discussion.
