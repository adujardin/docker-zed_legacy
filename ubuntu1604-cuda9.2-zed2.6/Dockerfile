# Use an official Python runtime as a parent image
FROM nvidia/cuda:9.2-devel-ubuntu16.04

# Install any needed packages specified in requirements.txt
RUN apt-get update
RUN apt-get install lsb-release wget less udev sudo apt-transport-https -y
RUN wget -O ZED_SDK_Linux_Ubuntu16.run https://download.stereolabs.com/zedsdk/2.6/ubuntu 
RUN echo ttf-mscorefonts-installer msttcorefonts/accepted-mscorefonts-eula select true | sudo debconf-set-selections
RUN chmod +x ZED_SDK_Linux_Ubuntu16.run ; ./ZED_SDK_Linux_Ubuntu16.run silent
