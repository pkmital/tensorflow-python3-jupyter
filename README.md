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
$ docker run -it -p 8888:8888 -p 6006:6006 -v /$(pwd)/tensorflow:/notebooks --name tf pkmital/tf.0.9.0-py.3.4
```

On OSX, I discard the "/" just before the $(pwd).  On Windows, make sure to include it!  This command will download everything you need to run Tensorflow on a virtual machine.  If all succeeds, you will have a prompt like this:

```
$ docker run -it -p 8888:8888 -p 6006:6006 -v /$(pwd)/tensorflow:/notebooks --name tf pkmital/tf.0.9.0-py.3.4
Unable to find image 'pkmital/tf.0.9.0-py.3.4:latest' locally
latest: Pulling from pkmital/tf.0.9.0-py.3.4
5c90d4a2d1a8: Pull complete
ab30c63719b1: Pull complete
c6072700a242: Pull complete
abb742d515b4: Pull complete
7663bd2e167e: Pull complete
e0dfa7c8ceb7: Pull complete
5aec32f9504c: Pull complete
bf8f259657b7: Pull complete
97f51c760d42: Pull complete
88da4ac024f1: Pull complete
9be9261b300b: Pull complete
cbefc84e4f35: Pull complete
17c100eff420: Pull complete
a56c90619980: Pull complete
Digest: sha256:01cdde18a2838f819fd72c50fba9837bcde65017bf25261e1c978014c43280e9
Status: Downloaded newer image for pkmital/tf.0.9.0-py.3.4:latest
```

The next time you want to start this machine, you will launch the docker quickstart terminal and then write:

```
$ cd
$ docker start -i tf
```

As a result of this, you should have a new folder "tensorflow" inside your Home directory.  Make sure you do everything inside this directory only or else any files you make on your virtual machine WILL BE ERASED once it is shutdown!  In case you did forget this, you can always find your previous docker instance by running:

```
$ docker ps -a
CONTAINER ID        IMAGE                                 COMMAND             CREATED             STATUS                       PORTS               NAMES
182bd64f27d2        some/container   "/bin/bash"         About an hour ago   Exited (130) 6 seconds ago                       tf
```

And you can launch this container ID or clone it to retrieve any files you might have forgotten.
