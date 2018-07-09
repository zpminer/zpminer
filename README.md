# ZpMiner
Zen Protocol miner for GPU (AMD or NVidia) and CPU on Windows or Ubuntu. This miner currently solo mines to your local wallet and 2% of the time mines to the developer's wallet. Your found blocks are immediately shown in your wallet, because your coin base address is used for mining.


## FAQ
* How do I set up a local wallet to mine in to?
  - Install a [ZenProtocol Wallet](https://github.com/zenprotocol/zenwallet) here. Use the wallet to setup an account and sync with the network. By default, the local mining endpoint is http://localhost:11567
* ZpMiner exits immediately with an error?
  - Check if your GPU are on platform 0 or not. If your GPU are on platform 1 or 2, set p=1 or p=2. The default is p=0.
* Do I need to set an address on the command line?
  - Yes, you need to provide some value as an argument on the command line, but it does not need to be your real address. Since zpminer currently only mines to your local wallet with your local coinbase address, the address set on the command line is not used. It's a place holder for the future when integration with pools has been completed.
* When do I get paid?
  - Zpminer currently mines only to your wallet, so any blocks you find are immediately credited to your wallet because the found block uses your address as the coin base address for the block you found. Zen Protocol wallets won't let you spend those ZP until they have been confirmed 100 blocks, but that's not a feature that zpminer can control.
* How do I set alternate mining urls?
  - u=http://localhost:11567


## Windows

### NVidia Run Dependencies
* Install Cuda 9.1 (includes OpenCL)

### AMD Run Dependencies
* Install [AMD OpenCL](https://support.amd.com/en-us/kb-articles/Pages/OpenCL2-Driver.aspx)

### Releases

   [Windows Release Zip](https://github.com/zpminer/zpminer/releases)


### Run

Example:
```
zpminer.exe zen1q47hqdlpn9yuq77dj6t23f9yu9apms4286qu6j5q3nc9xd33sq8cs0mldqv u=http://localhost:11567
```

Template:
```
zpminer.exe <MinerAddress>.<OptionalWorkerId> <Option>=<OptionValue>
```
* DeviceIds: Default is ALL, d=0,1,2,3,4 or d=all
* PlatformId: Default is 0. p=0
* Cpu Mining Threads: Default is 0. c=4
* PoolUrl: Default is localhost:11567. u=http://localhost:11567
* SuffixMax: Default is 8192. Max is 65536. s=8192
* DevFeePercent: Default is 2. Available 2 and up. df=2

## Linux

### Install dependencies

```
sudo apt-get install libcpprest-dev libncurses5-dev libssl-dev unixodbc-dev g++ git
```

### NVidia Install CUDA9.1 (includes OpenCL)

```
wget http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/cuda-repo-ubuntu1604_9.1.85-1_amd64.deb
sudo apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub
sudo dpkg -i cuda-repo-ubuntu1604_9.1.85-1_amd64.deb
sudo apt update
sudo apt install cuda -y
```

### AMD Install OpenCL
```
sudo apt-get install libclc-amdgcn mesa-opencl-icd
```

### Install release

```
- Ubuntu16
wget https://github.com/zpminer/zpminer/releases/download/1.7/zpminer_Ubuntu16_1.7.tar.gz
tar -xzvf zpminer_Ubuntu16_1.7.tar.gz

- Ubuntu17
wget https://github.com/zpminer/zpminer/releases/download/1.7/zpminer_Ubuntu16_1.7.tar.gz
tar -xzvf zpminer_Ubuntu17_1.5.tar.gz

```

### Run

Example:
```
./zpminer zen1q47hqdlpn9yuq77dj6t23f9yu9apms4286qu6j5q3nc9xd33sq8cs0mldqv u=http://localhost:11567
```
