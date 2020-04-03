
# UFOMiner ("x17r algo")

Nvidia GPU Support Only


## How to build (Windows Only)

1. Install Visual Studio >= 2013 (suggest to use MSVC toolset v120)

2. Download and Install CUDA 9.1 (https://developer.nvidia.com/cuda-91-download-archive)

3. `git clone https://github.com/ufo-project/UfoMiner`

4. `cd UfoMiner`

5. Open project **UfoMiner.vcxproj**

6. Start to build and wait to done


## How to Use (Windows Only)

1. Before mining, you should make sure you have a miner with Nvidia GPU

2. Install Nvidia GPU latest Driver

3. Start to mine

```UfoMiner.exe --url=stratum+tcp://mainnet-pool01.ufo.link:8080 --user=<your address>.<your name> --pass=<your pass>```

for example:

```UfoMiner.exe --url=stratum+tcp://mainnet-pool01.ufo.link:8080 --user=1f4d22bab09fdfdc1f4247a48f58396a3f3b15f8150748c5ac1c6f2189536728ca6.worker01 --pass=123456```



