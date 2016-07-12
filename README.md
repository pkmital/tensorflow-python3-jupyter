Tensorflow Python3 Jupyter
==========================

# Docker Toolbox

Docker is a way of launching "virtual" machines on your computer which will aid the creation a machine capable of running tensorflow.  In order to get up to speed with Tensorflow, please install the Docker Toolbox:

https://www.docker.com/products/docker-toolbox

You'll then need to run the "Docker Quickstart Terminal" which will launch a Terminal environment inside a Virtual Machine running on your computer.  Once the terminal is launched, run the following command:

```
$ cd
$ docker-machine ip
```

This is the virtual machine's IP address, or location on your private network.  NOTE THIS IP ADDRESS!  As we'll need it in a second.  Now run:

```
$ docker run -it -p 8888:8888 -p 6006:6006 -v /$(pwd)/tensorflow:/notebooks --name tf pkmital/tensorflow-python3-jupyter
```

On OSX, I discard the "/" just before the $(pwd).  On Windows, make sure to include it!  This command will download everything you need to run Tensorflow on a virtual machine.  If all succeeds, you will have a prompt like this:

The next time you want to start this machine, you will launch the docker quickstart terminal and then write:

```
$ cd
$ docker start -i tf
```

As a result of this, you should have a new folder "tensorflow" inside your Home directory.  Make sure you do everything inside this directory only or else any files you make on your virtual machine WILL BE ERASED once it is shutdown!
