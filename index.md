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

### Install [Anaconda](https://www.continuum.io/downloads) on mac:
There are two methods to install Anaconda,including graphical installer and command line. It also depends on what kind of version of Python you use. For example, my version of python is 3.6, I choose Anaconda3-4.3.0-MacOSX-x86_64.sh to install.

Note: if you install Anaconda through commond line, the folder of Anaconda is called "anaconda3"  
Note: if you use graphical installer, the folder of Anaconda is called "anaconda"  



### In order to avoid some errors, I install python 3.5 for sure. 
### Create virtual environment for installing tensorflow by this command line:
```
conda create -n yourenvname python=3.5 anaconda 
```
### Invoke your environment by this command line:

```
source activate yourenvname
```

