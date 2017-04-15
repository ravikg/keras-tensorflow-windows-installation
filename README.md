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

Put your unzipped folder in C drive as follows: 
```Command Prompt
C:\cudnn-8.0-windows10-x64-v5.1
```
### Step 5: Add cuDNN into Environment PATH <a href="https://kb.wisc.edu/cae/page.php?id=24500" target="_blank">Tutorial</a>

Add the following path in your Environment.
Subjected to changes in your installation path.
```Command Prompt
C:\cudnn-8.0-windows10-x64-v5.1\cuda\bin
```

Turn off all the prompts. 
Open a new Anaconda Prompt to type the following command(s)
```Command Prompt
echo %PATH%
```
You shall see that the new Environment PATH is there.

### Step 6: Create an Anaconda environment with Python=3.5
Open Anaconda Prompt to type the following command(s)
```Command Prompt
conda create -n tensorflow python=3.5 numpy scipy matplotlib spyder
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

### Step 10: Testing
Let's try running <a href="https://github.com/antoniosehk/keras-tensorflow-windows-installation/blob/master/examples/mnist_mlp.py">mnist_mlp.py</a> in your prompt.

Open Anaconda Prompt to type the following command(s)
```Command Prompt
activate tensorflow
python mnist_mlp.py
```
Congratulations ! You have successfully run Keras (with Tensorflow backend) over GPU on Windows !
