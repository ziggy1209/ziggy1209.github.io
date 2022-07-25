# Tensorflow Software Compatibility 

Make sure to follow the Tensorflow compatibility guideline https://www.tensorflow.org/install/source#gpu when installing/upgrading softwares.

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

CUDA:
```bash
cat /usr/local/cuda/version.txt
```
or
```bash
nvcc --version
```
