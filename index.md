## HTTP-eror-404 while getting https https://storage.googleapis.com/tensorflow/mac/......

when I follow the guide from [Installing TensorFlow on Mac OS X](https://www.tensorflow.org/install/install_mac)to install tensorflow, I got the error as below:

```
HTTP error 404 while getting https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl
  Could not install requirement tensorflow-gpu==1.0.1 from https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl because of error 404 Client Error: Not Found for url: https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl
Could not install requirement tensorflow-gpu==1.0.1 from https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl because of HTTP error 404 Client Error: Not Found for url: https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl for URL https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl

```
- my OS version on mac: 10.10.5
- python: 3.5.2 in : Anaconda custom (x86_64)

### Try type this commond line to know your version of python :
``` 
$ python --version
Python 3.6.0 :: Anaconda 4.3.0 (x86_64)
```

### 1. Install [Anaconda](https://www.continuum.io/downloads) on mac:
There are two methods to install Anaconda,including graphical installer and command line. It also depends on what kind of version of Python you use. For example, my version of python is 3.6, I choose Anaconda3-4.3.0-MacOSX-x86_64.sh to install.

- Note: if you install Anaconda through commond line, the folder of Anaconda is called "anaconda3"  
- Note: if you use graphical installer, the folder of Anaconda is called "anaconda"  

In order to avoid some errors, I install python 3.5 for sure. Soemtimes it has some problems when I use python 3.6 for tensorflow. 

### 2. Create virtual environment for installing tensorflow by this command line:
```
conda create -n yourenvname python=3.5 anaconda 
```
### 3. Invoke your environment by this command line:

```
source activate yourenvname
```
### 4. According to the [giude of installing tensorflow in mac](https://www.tensorflow.org/install/install_mac), the next step is to install tensorflow into your environment:

```
pip install --ignore-installed --upgrade $TF_PYTHON_URL 
```
- [$TF_PYTHON_URL](https://www.tensorflow.org/install/install_mac#TF_PYTHON_URL), it depends on your version of python, CPU and GPU.

If you get an error which is like as below:
```
HTTP error 404 while getting https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl
  Could not install requirement tensorflow-gpu==1.0.1 from https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl because of error 404 Client Error: Not Found for url: https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl
Could not install requirement tensorflow-gpu==1.0.1 from https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl because of HTTP error 404 Client Error: Not Found for url: https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl for URL https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl

```
Try this one (for gpu support):
```
sudo pip3 install tensorflow-gpu
```
or this one (for cpu support)
```
sudo pip3 install tensorflow
```
- Note: If you version of Python is 2.7, use `pip` instead of `pip3` 

### 5. Let's check our installation:
```
$python
Python 3.5.2 |Anaconda custom (x86_64)| 
[GCC 4.2.1 Compatible Apple LLVM 4.2 (clang-425.0.28)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import tensorflow as tf
>>> hello = tf.constant('Hello, TensorFlow!')
>>> sess = tf.Session()
>>> print(sess.run(hello))
b'Hello, testing TensorFlow!'
```
- Note: Make sure that there are no name of file or name of folder is `tensorflow` in your current directory. 
For example, if I type 'python' inide the directory of desktop and there is a folder named as `tensorflow`, it could cause this error:

```
>>> hello = tf.constant('Hello, TensorFlow!')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
AttributeError: module 'tensorflow' has no attribute 'constant'
```
Change your current directory to another directory that help you solve this problem. For example, use `cd ..` command line goinf to upper level directory.

- Note : After installing tensorflow in this virtual environment, we only can use tensorflow in this virtual environment. If you import tensorflow outside of this virtual environment, it could cause this error:
```
$ python
Python 3.6.0 |Anaconda 4.3.0 (x86_64)| 
[GCC 4.2.1 Compatible Apple LLVM 6.0 (clang-600.0.57)] on darwin
Type "help", "copyright", "credits" or "license" for more information.
>>> import tensorflow
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
ModuleNotFoundError: No module named 'tensorflow'
```
Also, if we have this error in the virtual environment, it means that we don't install tensorflow completely. I have encountered this error during installation. I suggest that remove whole Anaconda folder, and install by these several steps.


Reference: https://www.tensorflow.org/install/install_mac

Reference: http://stackoverflow.com/questions/37383812/tensorflow-module-object-has-no-attribute-placeholder
