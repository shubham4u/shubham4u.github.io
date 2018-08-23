# Install Tensorflow on Ubuntu 16.04

(I have done it in VirtualBox 5.2.18 and tested on both VMware 14 as well as VirtualBox 5.2.18)

step 1 : Install Python & pip
On Ubuntu, Python is automatically installed and pip is usually installed. Confirm the python and pip versions:
```sh
  $ python -V  # or: python3 -V
  $ pip -V     # or: pip3 -V
```
step 2: If not install then follow the below commands
```sh
  $ sudo apt-get install python-pip python-dev   # for Python 2.7
  $ sudo apt-get install python3-pip python3-dev # for Python 3.n
```
Step 3: We need upgraded pip version, to upgrade pip:
```sh
    $ sudo pip install -U pip
```
Step 4: Now, To Install Tensorflow packages for Python 2 or 3: 
```sh
    $ sudo pip install -U tensorflow   # Python 2.7
    $ sudo pip3 install -U tensorflow  # Python 3.n
```
Step 5: At the last check the test version of TF:
```sh
    $ python -c "import tensorflow as tf; print(tf.__version__)"
```

# CNTK

## Required Packages for cntk
### *OPENMPI*
CNTK requires OpenMPI 1.10.x to be installed on your system. On Ubuntu 16.04 install it like this:
```sh
    $ sudo apt-get install openmpi-bin
```
***Installation of CNTK***
I had used wheel(.whl) files to install cntk2.5.1
```sh
   $ wget https://cntk.ai/PythonWheel/CPU-Only/cntk-2.5.1-cp36-cp36m-linux_x86_64.whl
   $ sudo pip install cntk-2.5.1-cp36-cp36m-linux_x86_64.whl
```
At the last check the installation version of cntk:
```sh
    $ python -c "import cntk; print(cntk.__version__)"
```
# PyCaffe
### *Genereal dependencies*
```sh
    $ sudo apt-get install libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libhdf5-serial-dev protobuf-compiler
    $ sudo apt-get install --no-install-recommends libboost-all-dev
```
**BLAS**:To install ATLAS
```sh
    $ sudo apt-get install libatlas-base-dev
```
## Required Packages python modules for caffe ##
```sh
    $ mkdir /shubham  
    $ cd /shubham
    $ git clone https://github.com/BVLC/caffe.git
    $ cd /shubham/caffe/python
    $ for req in $(cat requirements.txt); do pip install $req; done
    $ python -m sites 
```
## Compilation ##
```sh
    $ cd /shubham
    $ cp Makefile.config.example Makefile.config
```
**Adjust Makefile.config**
    * For CPU only
* CPU_ONLY := 1  {Remove commment at line no. 8}
* WITH_PYTHON_LAYER=1 {Remove comment at line no. 92}
**Make**
```sh
    $ make all
    $ make test
    $ make runtest
    $ make pycaffe 
    $ make pytest  
```
In order to make the Python work with Caffe, open the file ~/.bashrc for editing in the text editor. There, add the following line at the end of file:
```sh
    $ export PYTHONPATH=/path/to/caffe-master/python:$PYTHONPATH
    $ source ~/.bashrc 
```
At the last check the the module is installed or not
```sh
    $ cd /shubham/caffe/python
    $ python -c "import caffe" 
```
I have created a (.iso) which consist of these three python module inbuild.
link is :-   

```sh
https://drive.google.com/open?id=1braCkztCtfxLnoWz0AyLtqj-D1WA0ho5
```







