# Abstract
Caffe is a deep learning framework developed by Berkeley AI Research (BAIR) that is used in scientific research and engineering. It is an open-source software library written in C++, with a Python interface, and is designed for efficiency and speed in training and deploying deep neural networks. Caffe is widely used in a variety of applications, such as **image classification, object detection, speech recognition, and natural language processing**. It has been used in numerous scientific studies, including in the fields of astronomy, biology, and medical imaging, and is also used by major technology companies such as Google, Microsoft, and NVIDIA. Caffe can be considered as a programming tool and a "middleware" between the user and the hardware, providing a flexible and efficient platform for building and deploying deep learning models.

# Installation
First, make sure you have the required dependencies installed on your system:

    sudo apt-get update
    sudo apt-get upgrade
    sudo apt-get install libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libhdf5-serial-dev protobuf-compiler
    sudo apt-get install --no-install-recommends libboost-all-dev
Next, download the Caffe source code from the official GitHub repository:

    git clone https://github.com/BVLC/caffe.git
    cd caffe
Copy the Makefile.config.example file to create the Makefile.config file:

    cp Makefile.config.example Makefile.config

Note: The settings can be modified as necessary by opening the Makefile.config, for example, if you want to use the CPU version of Caffe, uncomment the CPU_ONLY := 1 line.

Now, you can build Caffe. This will compile Caffe with 2 threads. If you have more or less cores, adjust the -j flag accordingly.:

    make all -j2

After the build is complete, run the tests to make sure everything is working properly:

    make test -j2

(OPTIONAL) If you want to install Caffe system-wide, run:

    make install 

This will copy the Caffe binaries to /usr/local/bin/caffe.

And that's it! You should now have Caffe installed on your Linux system.

# Example Code
Download the dataset:

    wget https://www.cs.toronto.edu/~kriz/cifar-10-binary.tar.gz
    tar -xzvf cifar-10-binary.tar.gz
Download the .prototxt that defines a fully-connected neural network with one hidden layer (fc1) and a softmax output layer (loss).

    wget https://www.github.com/johnnyoko/parallelized_primes/cifar10_quick_train_test.prototxt

Convert the dataset to LMDB format:

    ~/caffe/build/tools/convert_cifar_data.bin data/cifar10 data/cifar10/cifar_train.bin data/cifar10/cifar_mean.binaryproto
    
To train and test the network, you can use the same commands as before:

    $ ./build/tools/caffe train --solver=examples/my_example/solver.prototxt
    $ ./build/tools/caffe test --model=examples/my_example/my_net.prototxt --weights=examples/my_example/my_net_iter_10000.caffemodel --iterations=100
Note that the paths to the solver and network files may be different depending on where you saved them.     

cifar10_quick_train_test.prototxt defines a fully-connected neural network with one hidden layer (fc1) and a softmax output layer (loss). The accuracy layer is used to calculate the classification accuracy during testing.
       
        



# References 
Caffe's official website: http://caffe.berkeleyvision.org/

Caffe installation instructions on GitHub: https://github.com/BVLC/caffe/blob/master/INSTALL.md

NVIDIA CUDA Toolkit installation guide: https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html

NVIDIA cuDNN installation guide: https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html

OpenBLAS installation guide: https://github.com/xianyi/OpenBLAS/wiki/Installation-Guide

HDF5 installation guide: https://support.hdfgroup.org/HDF5/Tutor/installation.html

Python and its libraries (NumPy, SciPy, matplotlib) can be installed using pip or conda.
