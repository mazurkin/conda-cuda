# nvcc

```shell
$ make env-init
$ make env-create
```

```shell
$ make env-shell
```

## conda + nvidia

https://anaconda.org/anaconda/cuda-toolkit/files
https://anaconda.org/anaconda/cudnn/files

## nvcc samples

https://cuda-tutorial.readthedocs.io/en/latest/tutorials/tutorial01/
https://cuda-tutorial.readthedocs.io/en/latest/tutorials/tutorial01/solutions/vector_add.cu

```shell
$ nvcc samples/vector_add.cu -o samples/target/vector_add
$ samples/target/vector_add
```

## cudnn sample

https://github.com/Hardware-Alchemy/cuDNN-sample/tree/master/home-made

```shell
$ nvcc helloworld.cpp -I $CONDA_PREFIX/include -L $CONDA_PREFIX/lib -lcudnn -o sample
$ ./sample
```


