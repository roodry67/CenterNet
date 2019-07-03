# Installation


The code was tested on Ubuntu 16.04, with [Anaconda](https://www.anaconda.com/download) Python 3.6 and [PyTorch]((http://pytorch.org/)) v0.4.1. NVIDIA GPUs are needed for both training and testing.
After install Anaconda:

0. [Optional but recommended] create a new conda environment. 

    ~~~
    conda create --name CenterNet python=3.6
    ~~~
    And activate the environment.
    
    ~~~
    conda activate CenterNet
    ~~~

1. Install pytorch0.4.1:

    ~~~
    conda install pytorch torchvision -c pytorch
    ~~~
    

2. Clone this repo:

    ~~~
    CenterNet_ROOT=/path/to/clone/CenterNet
    git clone https://github.com/roodry67/CenterNet.git $CenterNet_ROOT
    git submodule update --init
    ~~~


4. Install the requirements

    ~~~
    pip install -r requirements.txt
    ~~~
    
    
5. Compile deformable convolutional (from [DCNv2](https://github.com/CharlesShang/DCNv2/tree/pytorch_0.4)).

    ~~~
    cd $CenterNet_ROOT/src/lib/models/networks/DCNv2
    ./make.sh
    ~~~
6. [Optional] Compile NMS if your want to use multi-scale testing or test ExtremeNet.

    ~~~
    cd $CenterNet_ROOT/src/lib/external
    make
    ~~~

7. Download pertained models for [detection]() or [pose estimation]() and move them to `$CenterNet_ROOT/models/`. More models can be found in [Model zoo](MODEL_ZOO.md).
