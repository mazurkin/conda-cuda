# nvcc

```shell
$ make env-init
$ make env-create
```

```shell
$ make env-shell
```

## hardware

```shell
$ nvidia-smi
Thu Oct 10 11:28:29 2024
+-----------------------------------------------------------------------------------------+
| NVIDIA-SMI 550.107.02             Driver Version: 550.107.02     CUDA Version: 12.4     |
|-----------------------------------------+------------------------+----------------------+
| GPU  Name                 Persistence-M | Bus-Id          Disp.A | Volatile Uncorr. ECC |
| Fan  Temp   Perf          Pwr:Usage/Cap |           Memory-Usage | GPU-Util  Compute M. |
|                                         |                        |               MIG M. |
|=========================================+========================+======================|
|   0  NVIDIA RTX 3500 Ada Gene...    Off |   00000000:01:00.0  On |                  Off |
| N/A   40C    P8              9W /  115W |     110MiB /  12282MiB |     35%      Default |
|                                         |                        |                  N/A |
+-----------------------------------------+------------------------+----------------------+

+-----------------------------------------------------------------------------------------+
| Processes:                                                                              |
|  GPU   GI   CI        PID   Type   Process name                              GPU Memory |
|        ID   ID                                                               Usage      |
|=========================================================================================|
|    0   N/A  N/A      3396      G   /usr/lib/xorg/Xorg                            105MiB |
+-----------------------------------------------------------------------------------------+
```

```shell
$ nvidia-smi --query-gpu=compute_cap --format=csv
compute_cap
8.9

$ nvidia-smi --query-gpu=driver_version --format=csv
driver_version
550.107.02

$ nvidia-smi --query-gpu=gpu_name,gpu_bus_id,vbios_version --format=csv
name, pci.bus_id, vbios_version
NVIDIA RTX 3500 Ada Generation Laptop GPU, 00000000:01:00.0, 95.04.4B.00.07
```

```shell
$ uname -rv
6.8.0-45-generic #45~22.04.1-Ubuntu SMP PREEMPT_DYNAMIC Wed Sep 11 15:25:05 UTC 2
```

```shell
$ ldd --version
ldd (Ubuntu GLIBC 2.35-0ubuntu3.8) 2.35
```

## nvidia

- https://docs.nvidia.com/deeplearning/cudnn/latest/reference/support-matrix.html
- https://www.tensorflow.org/install/source#gpu

## conda + nvidia

- https://anaconda.org/nvidia/cuda-toolkit/files
- https://anaconda.org/anaconda/cudnn/files
- https://anaconda.org/main/cudnn/files

## samples

### nvcc samples

- https://cuda-tutorial.readthedocs.io/en/latest/tutorials/tutorial01/
- https://cuda-tutorial.readthedocs.io/en/latest/tutorials/tutorial01/solutions/vector_add.cu

```shell
$ nvcc samples/vector_add.cu -o samples/target/vector_add
$ samples/target/vector_add
```

### cudnn sample

- https://github.com/Hardware-Alchemy/cuDNN-sample/tree/master/home-made

```shell
$ nvcc helloworld.cpp -I "$CONDA_PREFIX/include" -L "$CONDA_PREFIX/lib" -lcudnn -o sample
$ ./sample
```


