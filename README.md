# Name
**ubuntu18-container-pycv-build**  
Docker remote container environment based on Ubuntu 18.04.  


# Overview
This is a repository for building a virtual development environment using Docker + VSCode (remote container).  
It is based on Ubuntu 18.04. Please rewrite the Dockerfile to use it if necessary.  
A container environment for Python development with opencv,   
which builds opencv when the Docker image is built.  

# Installation
```bash
docker build -t "Imagename" .  
# Windows
docker run -it --privileged -e DISPLAY=xx.xx.xx.xx:0.0 --name="Containername" Imagename  
# Ubuntu
docker run -it --privileged -e DISPLAY=$DISPLAY -v /tmp/.X11-unix/:/tmp/.X11-unix --name="Containername" Imagename  

```
or  
Open the container from the remote container feature of VScode.

# Demo
```bash
# The cat's image will be displayed.
python3 python3 /home/project/sample_src/sample.py  

```

# Note
T.B.D.  

# Author
* AIRO
* "https://twitter.com/AIRO28_"

# Licence
This repository is Confidential
