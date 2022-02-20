# Ubuntu-Bitcoin-Node

___
Bitcoin source code: https://github.com/bitcoin/bitcoin
___

## Hardware

| Component     | Model     |
|:--------------|:----------|
| Motherboard | Gigabyte B450M DS3H |
| RAM | Corsair Vengeance LPX 16GB |
| CPU | AMD Ryzen 3 1200 |
| CPU Cooler | *Fan came with CPU |
| Power Supply | ARESGAME 500W Power Supply |
| GPU | AMD Radeon 6600 XT |
| Storage | WD Black Series 500 GB HDD |

I purchased these components on Amazon or BestBuy & used the following site to help pick each of them out!
https://pcpartpicker.com/


## OS

Ubuntu 20.04

### To install Ubuntu on a bare metal PC:
1. On a separate PC, download Ubuntu https://ubuntu.com/download/desktop
2. Download Rufus https://rufus.ie/en/
3. Insert a USB storage device and use Rufus to turn it into an Ubuntu bootable
4. Plug the USB into your new PC and turn it on
5. Select Ubuntu
6. You can choose to try it first or install it - eventually you want to install it
7. When you install Ubuntu, you’ll want to select Minimal Installation and uncheck the boxes for updates & third-party software

## Bitcoin Node Configuration

#### 1. Update repositories and install `git`.
```shell
sudo apt update
sudo apt-get update
sudo apt install -y git
```

#### 2. Download all dependencies for Bitcoin.
```shell
sudo apt-get install -y build-essential libtool autotools-dev automake pkg-config bsdmainutils python3
sudo apt-get install -y libevent-dev libboost-dev libboost-system-dev libboost-filesystem-dev libboost-test-dev

# Install SQLLite for wallet
```shell
sudo apt install -y libsqlite3-dev
```

##### Port-mapping libraries
```shell
sudo apt install -y libminiupnpc-dev libnatpmp-dev
```

##### ZMQ dependencies
```shell
sudo apt-get install -y libzmq3-dev
```

##### User-Space, Statically Defined Tracing
```shell
sudo apt install -y systemtap-sdt-dev
```

##### GUI Dependencies
```shell
sudo apt-get install -y libqt5gui5 libqt5core5a libqt5dbus5 qttools5-dev qttools5-dev-tools
```

##### Support for Wayland protocol
```shell
sudo apt install -y qtwayland5
```

#### 3. Clone the Bitcoin repository from GitHub
```shell
git clone https://github.com/bitcoin/bitcoin.git
```

#### 4. Configure the Bitcoin Core install
```shell
cd bitcoin
sudo bash autogen.sh
sudo ./configure
```

#### 5. Install Bitcoin Core
```shell
cd src
sudo make install
```
