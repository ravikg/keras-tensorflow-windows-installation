# keras-tensorflow-windows-installation
This is a repository for tutoring the installation of Tensorflow with GPU support in Windows

### Step 1: Install Anaconda (Python 3.6 version) <a href="https://www.continuum.io/downloads" target="_blank">Download</a>
<p align="center"><img width=60% src="https://github.com/antoniosehk/keras-tensorflow-windows-installation/blob/master/anaconda_windows_installation.png"></p>

### Step 2: Open the Anaconda prompt

```Command Prompt
conda update conda
conda update --all
```

### Step 3: Install CUDA
### Install cuDNN

# Add to PATH
# C:\Users\Antonio\cudnn-8.0-windows10-x64-v5.1\cuda\bin
# echo %PATH%

### Create a Python 3.5 environment
```Command Prompt
conda create -n tensorflow python=3.5 numpy scipy matplotlib
```

### Activate the environment
```Command Prompt
activate tensorflow
```

### Install TensorFlow-GPU-1.0.1
```Command Prompt
pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/windows/gpu/tensorflow_gpu-1.0.1-cp35-cp35m-win_amd64.whl
```

### Install Keras
```Command Prompt
pip install keras
```


