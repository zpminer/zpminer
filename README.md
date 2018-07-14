# ZpMiner
Zen Protocol miner for GPU (AMD or NVidia) and CPU on Windows or Ubuntu. ZpMiner is free to use and has a minimum 1% dev fee.


## FAQ
* Why does ZpMiner exits immediately with an error?
  - Check if your GPU are on platform 0 or not. If your GPU are on platform 1 or 2, set p=1 or p=2. The default is p=0.
* Can I cpu only mine with ZpMiner?
  - Yes, set d=NONE and c=4 or whatever CPU mining thread number you want. If it complains about missing OpenCL.dll, get that and drop it in the zpminer folder. The zpMiner release assumes you have OpenCL installed already.
* How do I set the dev fee to 1%?
  - Set the df argument to 1: df=1


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
zpminer.exe zen1q47hqdlpn9yuq77dj6t23f9yu9apms4286qu6j5q3nc9xd33sq8cs0mldqv u=stratum+tcp://zp-us-east.leafpool.com:8811
```

Template:
```
zpminer.exe <MinerAddress>.<OptionalWorkerId> <Option>=<OptionValue>
```
* DeviceIds: Default is ALL, d=0,1,2,3,4 or d=all
* PlatformId: Default is 0. p=0
* Cpu Mining Threads: Default is 0. c=4
* PoolUrl: Default is stratum+tcp://zp-us-east.leafpool.com:8811. u=stratum+tcp://zp-us-east.leafpool.com:8811
* SuffixMax: Default is 8192. Max is 65536. s=8192
* DevFeePercent: Default is 2. Available 1 and up. df=1
* Stratum Password: Deafult is x. x=password

## Linux

### Install dependencies

```
sudo apt-get install libcpprest-dev libncurses5-dev libssl-dev unixodbc-dev g++ git libcurl4-gnutls-dev libjansson-dev
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
wget https://github.com/zpminer/zpminer/releases/download/2.0/zpminer_Ubuntu16_1.7.tar.gz
tar -xzvf zpminer_Ubuntu16_2.0.tar.gz

- Ubuntu17
wget https://github.com/zpminer/zpminer/releases/download/2.0/zpminer_Ubuntu16_1.7.tar.gz
tar -xzvf zpminer_Ubuntu17_2.0.tar.gz

```

### Run

Example:
```
./zpminer zen1q47hqdlpn9yuq77dj6t23f9yu9apms4286qu6j5q3nc9xd33sq8cs0mldqv u=stratum+tcp://zp-us-east.leafpool.com:8811
```
