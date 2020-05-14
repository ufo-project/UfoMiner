
# UFOMiner ("x17r algo")

Nvidia GPU Support Only


## How to build (Windows)

1. Install Visual Studio >= 2013 (suggest to use MSVC toolset v120)

2. Install latest Nvidia Driver

3. Download and Install CUDA 9.1 (https://developer.nvidia.com/cuda-91-download-archive)

4. `git clone https://github.com/ufo-project/UfoMiner`

5. `cd UfoMiner`

6. Open project **UfoMiner.vcxproj**

7. Start to build and wait to done


## How to build (Ubuntu 18.04)

1. Install build tools and dependencies

```
sudo apt-get update
sudo apt-get install build-essential autoconf git
sudo apt-get install libssl-dev
sudo apt-get install libcurl4-openssl-dev
```

2. Install latest Nvidia Driver


```
# Blacklist Nvidia nouveau driver

sudo bash -c "echo blacklist nouveau > /etc/modprobe.d/blacklist-nvidia-nouveau.conf"
sudo bash -c "echo options nouveau modeset=0 >> /etc/modprobe.d/blacklist-nvidia-nouveau.conf"

sudo update-initramfs -u
sudo reboot
```


```
sudo rm /etc/apt/sources.list.d/cuda*
sudo apt remove --autoremove nvidia-cuda-toolkit
sudo apt remove --autoremove nvidia-*

sudo apt update
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-driver-440
```


3. Install CUDA for linux

```
sudo apt-key adv --fetch-keys  http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/7fa2af80.pub
sudo bash -c 'echo "deb http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64 /" > /etc/apt/sources.list.d/cuda.list'
sudo bash -c 'echo "deb http://developer.download.nvidia.com/compute/machine-learning/repos/ubuntu1804/x86_64 /" > /etc/apt/sources.list.d/cuda_learn.list'

sudo apt update
sudo apt install cuda-10-1
sudo apt install nvidia-cuda-toolkit
```

4. Add the following lines to your ~/.profile file for CUDA 10.1
```
if [ -d "/usr/local/cuda-10.1/bin/" ]; then
    export PATH=/usr/local/cuda-10.1/bin${PATH:+:${PATH}}
    export LD_LIBRARY_PATH=/usr/local/cuda-10.1/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}
fi
```

5. Check NVIDIA Cuda Compiler with `nvcc --version`

6. Check NVIDIA driver with `nvidia-smi`


7. Fetch the ufominer project

```
git clone https://github.com/ufo-project/UfoMiner
cd UfoMiner
git clone https://github.com/ufo-project/curl-for-windows
```

8. build

```
sh autogen.sh
sh configure.sh
make -j4
```


## How to Use

1. Before mining, you should make sure you have a miner with Nvidia GPU

2. Install Nvidia GPU latest Driver

3. Start to mine

* windows


```UfoMiner.exe --url=stratum+tcp://mainnet-pool01.ufo.link:8080 --user=<your address>.<your name> --pass=<your pass>```

* linux


```./UfoMiner --url=stratum+tcp://mainnet-pool01.ufo.link:8080 --user=<your address>.<your name> --pass=<your pass>```

for example:

* windows


```UfoMiner.exe --url=stratum+tcp://mainnet-pool01.ufo.link:8080 --user=1f4d22bab09fdfdc1f4247a48f58396a3f3b15f8150748c5ac1c6f2189536728ca6.worker01 --pass=123456```

* linux


```./UfoMiner --url=stratum+tcp://mainnet-pool01.ufo.link:8080 --user=1f4d22bab09fdfdc1f4247a48f58396a3f3b15f8150748c5ac1c6f2189536728ca6.worker01 --pass=123456```

