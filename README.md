# Docker with the ZED SDK

This images let you use the ZED SDK with docker, even with the ZED camera connected (or an SVO file)

## Getting started

### Setup Docker

Since we need CUDA, nvidia-docker must be used.

Follow the instructions at https://github.com/NVIDIA/nvidia-docker

Once nvidia-docker is installed, make sure it run fine by launching :

    nvidia-docker run --rm nvidia/cuda nvidia-smi

### Pull the image from docker hub

    docker pull adujardin/zed_sdk:ubuntu1604-cuda9.0-zed2.6
    nvidia-docker run -it --privileged adujardin/zed_sdk:ubuntu1604-cuda9.0-zed2.6

`--privileged` option is used to pass through all the device to the docker container, it might not be very safe but provides an easy solution to connect the USB3 camera to the container.

## Rebuilt or modifying the image

### Build the image

The image are based on cuda images from nvidia https://gitlab.com/nvidia/cuda/

The cuda version can easily be change, as the ZED SDK version.

Go to the folder with the version needed and run for instance :

    cd ubuntu1604-cuda9.0-zed2.6
    docker build -t zed_sdk:ubuntu1604-cuda9.0-zed2.6 .

### Run the local image

    nvidia-docker run -it --privileged zed_sdk:ubuntu1604-cuda9.0-zed2.6

The camera connection can be verified using lsusb:

    lsusb -d 2b03: -vvv

## Notes

Remainder for myself, to push an image :

    docker login --username=YourUserName
    docker push YourUserName/ImageName:ImageTag

### Limitations / TODO

- Their is currently no display on this containers

