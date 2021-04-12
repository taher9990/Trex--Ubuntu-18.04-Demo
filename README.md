## 2.1 DPDK Installation Using TRex Core
DPDK is the Data Plane Development Kit that consists of libraries to accelerate packet processing workloads running on a wide variety of CPU architectures.  Build DPDK with the commands below. </br>
```
wget https://github.com/cisco-system-traffic-generator/trex-core/archive/master.zip
unzip master.zip
cd trex-core-master/
cd linux_dpdk/
./b configure
./b build
Build DPDK kernel module igp_uio with the command below.
cd ..
cd scripts/ko/src/
make
sudo make install
sudo modprobe uio
sudo depmod -ae
sudo modprobe igb_uio
Add modules uio, igb_uio to the list of modules loaded after reboot.
sudo su
# echo "uio" >> /etc/modules
# echo "igb_uio" >> /etc/modules
```

## 1.2 TRex Installation

Download and extract the latest TRex.
```
mkdir trex
cd trex
wget https://trex-tgn.cisco.com/trex/release/latest --no-check-certificate

tar zxvf latest
cd ~/trex/v2.49/

```

Commands:
```
 sudo ./dpdk_nic_bind.py --status

```
