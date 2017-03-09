## HTTP-eror-404  from https://storage.googleapis.com/tensorflow/mac/......

when I follow the instruction from [Installing TensorFlow on Mac OS X](https://www.tensorflow.org/install/install_mac), I got the error as below:

```
HTTP error 404 while getting https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl
  Could not install requirement tensorflow-gpu==1.0.1 from https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl because of error 404 Client Error: Not Found for url: https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl
Could not install requirement tensorflow-gpu==1.0.1 from https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl because of HTTP error 404 Client Error: Not Found for url: https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl for URL https://storage.googleapis.com/tensorflow/mac/gpu/tensorflow_gpu-1.0.1-py3-none-any.whl

```
- my OS version on mac: 10.10.5
- python: 3.5.2 in :    Anaconda custom (x86_64)

Try type this commond to know your python version:
``` 
$ python --version
Python 3.6.0 :: Anaconda 4.3.0 (x86_64)
```




You can use the [editor on GitHub](https://github.com/qrslrhko/HTTP-error-404-tensorflow/edit/master/index.md) to maintain and preview the content for your website in Markdown files.


### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```


For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

