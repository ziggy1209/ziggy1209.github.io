# Tensorflow Software Compatibility 

Make sure to follow the [Tensorflow compatibility guideline](https://www.tensorflow.org/install/source#gpu) when installing/upgrading softwares.

Check the versions of related softwares:

Tensorflow:
```bash
pip3 show tensorflow
```

Python:
```bash
python --version
```

Compiler:
```bash
gcc --version
```

cuDNN:
```bash
cat /usr/local/cuda/include/cudnn.h | grep CUDNN_MAJOR -A 2
```
and then follow the calculation instruction.

Some newer versions of cuDNN write their information in `cudnn_version.h` instead of in `cudnn.h`, so it may be checked by
```bash
cat /usr/local/cuda/include/cudnn_version.h | grep CUDNN_MAJOR -A 2
```


CUDA:
```bash
cat /usr/local/cuda/version.txt
```
or
```bash
nvcc --version
```
While changing the version of CUDA currently in use, remember to export the path of the version wanted in `/etc/profile` or `~/.bashrc`, e.g.,
```bash
export PATH=/usr/local/cuda-xx.x/bin:$PATH
export LD_LIBRARY_PATH=/usr/local/cuda-xx.x/lib64:$LD_LIBRARY_PATH
```
