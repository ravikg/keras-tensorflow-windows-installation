# keras-tensorflow-windows-installation
This is a repository for tutoring the installation of Tensorflow with GPU support in Windows

### Step 1: Install Anaconda (Python 3.6 version) <a href="https://www.continuum.io/downloads" target="_blank">Download</a>
<p align="center"><img width=70% src="https://github.com/antoniosehk/keras-tensorflow-windows-installation/blob/master/anaconda_windows_installation.png"></p>

### Step 2: Update Anaconda
Open Anaconda Prompt to type the following command(s)
```Command Prompt
conda update conda
conda update --all
```

### Step 3: Install CUDA Tookit 8.0 <a href="https://developer.nvidia.com/cuda-downloads" target="_blank">Download</a>
Choose your version depending on your Operating System

<p align="center"><img width=70% src="https://github.com/antoniosehk/keras-tensorflow-windows-installation/blob/master/cuda8_windows7_local_installation.png"></p>

### Step 4: Download cuDNN <a href="https://developer.nvidia.com/rdp/cudnn-download" target="_blank">Download</a>
Choose your version depending on your Operating System.
Membership registration is required.

<p align="center"><img width=70% src="https://github.com/antoniosehk/keras-tensorflow-windows-installation/blob/master/cuDNN_windows_download.png"></p>

### Step 5: Add cuDNN into Enviroment PATH
### C:\Users\Antonio\cudnn-8.0-windows10-x64-v5.1\cuda\bin
### echo %PATH%

### Step 6: Create an Anaconda environment with Python=3.5
Open Anaconda Prompt to type the following command(s)
```Command Prompt
conda create -n tensorflow python=3.5 numpy scipy matplotlib
```

### Step 7: Activate the environment
Open Anaconda Prompt to type the following command(s)
```Command Prompt
activate tensorflow
```

### Step 8: Install TensorFlow-GPU-1.0.1
Open Anaconda Prompt to type the following command(s)
```Command Prompt
pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/windows/gpu/tensorflow_gpu-1.0.1-cp35-cp35m-win_amd64.whl
```

### Step 9: Install Keras
Open Anaconda Prompt to type the following command(s)
```Command Prompt
pip install keras
```


