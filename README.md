
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

3. Install CUDA for linux

4. Fetch the ufominer project

```
git clone https://github.com/ufo-project/UfoMiner
cd UfoMiner
git clone https://github.com/ufo-project/curl-for-windows
cd ..
```

5. build

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

