# Prepare for Raspberry PI

<strong><em>At the moment, QLauncher only supports to Raspberry Pi arm64 and amd64</em></strong>

### Enabling cgroups for Raspbian Buster
Standard Raspbian Buster installations do not start with `cgroups` enabled. **QLauncher** needs `cgroups` to start the systemd service. `cgroups` can be enabled by appending `cgroup_memory=1 cgroup_enable=memory` to `/boot/cmdline.txt`.


### example of /boot/cmdline.txt
```
console=serial0,115200 console=tty1 root=PARTUUID=58b06195-02 rootfstype=ext4 elevator=deadline fsck.repair=yes rootwait cgroup_memory=1 cgroup_enable=memory
```

### Enabling legacy iptables on Raspbian Buster
Raspbian Buster defaults to using `nftables` instead of iptables. **QLauncher** networking features require `iptables` and do not work with `nftables`. Follow the steps below to switch configure **Buster** to use `legacy iptables`:
```
sudo iptables -F
sudo update-alternatives --set iptables /usr/sbin/iptables-legacy
sudo update-alternatives --set ip6tables /usr/sbin/ip6tables-legacy
sudo reboot
```
