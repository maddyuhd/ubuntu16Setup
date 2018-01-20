Table of contents
=================

  * [Update](#update)
  * [Extras](#extras)
  * [Media](#media)
  * [Sublime Stuff](#sublime-stuff)
  * [Customize](#customize)
    * [Enable minimise on Click](#minimise-on-click)
  * [Theme](#theme)
    * [icon](#icon)
  * [Opencv](#opencv)
  * [TensorFlow](#tensorflow)
  

Update
=========
```shell
sudo apt-get update
sudo apt-get upgrade
sudo apt-get dist-upgrade
```
Extras
=========
```shell
sudo apt-get install ubuntu-restricted-extras
apt://flashplugin-installer
```
Media
=========
```shell
sudo apt install vlc
```

SublimeStuff
=========
```shell
sudo apt-get update
sudo apt-get install sublime-text
```

* "ctrl + shift + p" *install package control
* material theme
* anaconda
* advance new file
* sidebar enhancement

```shell
Linux - create "Default (Linux).sublime-mousemap" in ~/.config/sublime-text-3/Packages/User

Mac - create "Default (OSX).sublime-mousemap" in ~/Library/Application Support/Sublime Text 3/Packages/User

Win - create "Default (Windows).sublime-mousemap" in %appdata%\Sublime Text 3\Packages\User
```

```shell
[
    {
        "button": "button1", 
        "count": 1, 
        "modifiers": ["ctrl"],
        "press_command": "drag_select",
        "command": "goto_definition"
    }
]
```

Customize
=========
```shell
sudo apt-get install unity-tweak-tool
```

Terminal minimal
-----
```shell
nano ~/.bashrc
PS1="> "
PROMPT_COMMAND='echo -ne "\033]0;${USER}@${HOSTNAME}: ${PWD}\007"'
```

minimise on Click
-----
```shell
gsettings set org.compiz.unityshell:/org/compiz/profiles/unity/plugins/unityshell/ launcher-minimize-window true
```
Theme
=========
```shell
sudo sh -c "echo 'deb http://download.opensuse.org/repositories/home:/Horst3180/xUbuntu_16.04/ /' >> /etc/apt/sources.list.d/arc-theme.list"

sudo apt-get update && sudo apt-get install arc-theme

wget http://download.opensuse.org/repositories/home:Horst3180/xUbuntu_16.04/Release.key

sudo apt-key add - < Release.key
```
icon
-----
```shell
sudo add-apt-repository ppa:snwh/pulp
sudo apt-get update
sudo apt-get install paper-icon-theme
```

Opencv
=========
http://www.pyimagesearch.com/2016/10/24/ubuntu-16-04-how-to-install-opencv/
```shell
sudo apt-get install build-essential cmake pkg-config
sudo apt-get install libjpeg8-dev libtiff5-dev libjasper-dev libpng12-dev
sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
sudo apt-get install libxvidcore-dev libx264-dev
sudo apt-get install libgtk-3-dev
sudo apt-get install libatlas-base-dev gfortran

sudo apt-get install python2.7-dev python3.5-dev

cd ~
wget -O opencv.zip https://github.com/Itseez/opencv/archive/3.1.0.zip
unzip opencv.zip

wget -O opencv_contrib.zip https://github.com/Itseez/opencv_contrib/archive/3.1.0.zip
unzip opencv_contrib.zip
```

TensorFlow
=========
https://www.tensorflow.org/install/install_sources
```shell
git clone https://github.com/tensorflow/tensorflow 
cd tensorflow
git checkout r1.2

#Install JDK 8
sudo apt-get install openjdk-8-jdk


#Add Bazel distribution URI as a package source (one time setup)
echo "deb [arch=amd64] http://storage.googleapis.com/bazel-apt stable jdk1.8" | sudo tee /etc/apt/sources.list.d/bazel.list
curl https://bazel.build/bazel-release.pub.gpg | sudo apt-key add -

sudo apt-get update && sudo apt-get install bazel
sudo apt-get upgrade bazel

sudo apt-get install python-numpy python-dev python-pip python-wheel
```
# configuration
```shell
cd tensorflow  # cd to the top-level directory created
./configure
```
```shell
Please specify the location of python. [Default is /usr/bin/python]: /usr/bin/python2.7
Found possible Python library paths:
  /usr/local/lib/python2.7/dist-packages
  /usr/lib/python2.7/dist-packages
Please input the desired Python library path to use.  Default is [/usr/lib/python2.7/dist-packages]

Using python library path: /usr/local/lib/python2.7/dist-packages
Do you wish to build TensorFlow with MKL support? [y/N]
No MKL support will be enabled for TensorFlow
Please specify optimization flags to use during compilation when bazel option "--config=opt" is specified [Default is -march=native]:
Do you wish to use jemalloc as the malloc implementation? [Y/n]
jemalloc enabled
Do you wish to build TensorFlow with Google Cloud Platform support? [y/N]
No Google Cloud Platform support will be enabled for TensorFlow
Do you wish to build TensorFlow with Hadoop File System support? [y/N]
No Hadoop File System support will be enabled for TensorFlow
Do you wish to build TensorFlow with the XLA just-in-time compiler (experimental)? [y/N]
No XLA support will be enabled for TensorFlow
Do you wish to build TensorFlow with VERBS support? [y/N]
No VERBS support will be enabled for TensorFlow
Do you wish to build TensorFlow with OpenCL support? [y/N]
No OpenCL support will be enabled for TensorFlow
Do you wish to build TensorFlow with CUDA support? [y/N] Y
CUDA support will be enabled for TensorFlow
Do you want to use clang as CUDA compiler? [y/N]
nvcc will be used as CUDA compiler
Please specify the Cuda SDK version you want to use, e.g. 7.0. [Leave empty to default to CUDA 8.0]: 8.0
Please specify the location where CUDA 8.0 toolkit is installed. Refer to README.md for more details. [Default is /usr/local/cuda]:
Please specify which gcc should be used by nvcc as the host compiler. [Default is /usr/bin/gcc]:
Please specify the cuDNN version you want to use. [Leave empty to default to cuDNN 6.0]: 6
Please specify the location where cuDNN 6 library is installed. Refer to README.md for more details. [Default is /usr/local/cuda]:
Please specify a list of comma-separated Cuda compute capabilities you want to build with.
You can find the compute capability of your device at: https://developer.nvidia.com/cuda-gpus.
Please note that each additional compute capability significantly increases your build time and binary size.
[Default is: "3.5,5.2"]: 3.0
Do you wish to build TensorFlow with MPI support? [y/N] 
MPI support will not be enabled for TensorFlow
Configuration finished
```
# building
```shell
bazel build --config=opt //tensorflow/tools/pip_package:build_pip_package
bazel-bin/tensorflow/tools/pip_package/build_pip_package /tmp/tensorflow_pkg
sudo pip install /tmp/tensorflow_pkg/tensorflow-1.2.1-cp27-cp27mu-linux_x86_64.whl
```
# test
```shell
# Python 
import tensorflow as tf
hello = tf.constant('Hello, TensorFlow!')
sess = tf.Session()
print(sess.run(hello))
```
