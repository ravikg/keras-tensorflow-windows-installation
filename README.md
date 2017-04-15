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
You can run the following <a href="https://github.com/antoniosehk/keras-tensorflow-windows-installation/blob/master/examples/mnist_mlp.py">mnist_mlp.py</a> in your prompt.

```Python
'''Trains a simple deep NN on the MNIST dataset.
Gets to 98.40% test accuracy after 20 epochs
(there is *a lot* of margin for parameter tuning).
2 seconds per epoch on a K520 GPU.
'''

from __future__ import print_function

import keras
from keras.datasets import mnist
from keras.models import Sequential
from keras.layers import Dense, Dropout
from keras.optimizers import RMSprop


batch_size = 128
num_classes = 10
epochs = 20

# the data, shuffled and split between train and test sets
(x_train, y_train), (x_test, y_test) = mnist.load_data()

x_train = x_train.reshape(60000, 784)
x_test = x_test.reshape(10000, 784)
x_train = x_train.astype('float32')
x_test = x_test.astype('float32')
x_train /= 255
x_test /= 255
print(x_train.shape[0], 'train samples')
print(x_test.shape[0], 'test samples')

# convert class vectors to binary class matrices
y_train = keras.utils.to_categorical(y_train, num_classes)
y_test = keras.utils.to_categorical(y_test, num_classes)

model = Sequential()
model.add(Dense(512, activation='relu', input_shape=(784,)))
model.add(Dropout(0.2))
model.add(Dense(512, activation='relu'))
model.add(Dropout(0.2))
model.add(Dense(10, activation='softmax'))

model.summary()

model.compile(loss='categorical_crossentropy',
              optimizer=RMSprop(),
              metrics=['accuracy'])

history = model.fit(x_train, y_train,
                    batch_size=batch_size,
                    epochs=epochs,
                    verbose=1,
                    validation_data=(x_test, y_test))
score = model.evaluate(x_test, y_test, verbose=0)
print('Test loss:', score[0])
print('Test accuracy:', score[1])
```
