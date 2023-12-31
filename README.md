# Data visualization

## Objectives

This repository contains an app that does the following:

1. Face recognition
    
    **Objective**: Detect and track faces from a live webcam feed and compare them to a predefined collection of other faces.

    **Requirements**:
    - Detect faces in real-time from the webcam feed.
    - Capture a still frame of the detected face.
    - Compare the captured face to a collection of 40 other people.
    - Display the live camera feed, the extracted face, the top 5 most similar faces from the collection, and a numerical value representing their similarity (recognition score).

2. Image Processing + OCR (Optical Character Recognition)

    **Objective**: Develop an application that uses a live webcam feed to capture text from objects such as product labels, book titles, and packaging.

    **Requirements**:
    - Extract subsections of the image where text is detected.
    - Convert the extracted image text to unicode characters using OCR. 
    - Display the results on the screen, stacking them akin to a table format that juxtaposes the cropped images and their corresponding unicode text.

![](https://github.com/hugoescalpelo/data-visualization/blob/main/Images/Screenshot%20from%202023-10-18%2000-03-32.png?raw=true) 

## Quirks and features

This app is developed considering the following:
- **Variety**: Demonstrate multiple paradigms and programming languages usage.
- **Robustness**: modularity and interoperability.
- **Reproducibility**: easy installation and configuration in multiple devices.
- **Scalability**: multiple instances of this app can be runned in same device or many devices.
- **Mantainability**: detailed documentation and version control.
- **Openness**: all tools are well known and maintainded open source projects.

## Requirements

### Software
Here is a summary of software needed. Read instructions first, sequence and custom settings are needed. Each step include detailed instructions.

- [Ubuntu 22.04LTS](https://ubuntu.com/download/desktop). Also can be runned in any Debain Based distro, VM or WSL system.
- [CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit). Provides a development environment for creating high performance GPU-accelerated applications.
    - [cuDNN](https://developer.nvidia.com/cudnn).  Is a GPU-accelerated library of primitives for deep neural networks.
- [Visual Studio Code](https://code.visualstudio.com/). A code editor redefined and optimized for building and debugging modern web and cloud applications.
    - [Python Extension - Microsoft](https://github.com/Microsoft/vscode-python). A Visual Studio Code extension with rich support for the Python language.
- [Docker Engine](https://docs.docker.com/engine/install/ubuntu/). This allow to install with all dependencies provided by publisher.
    - [CodeProject.AI](https://hub.docker.com/r/codeproject/ai-server). This is an AI server for image recognition and will be installed via Docker Compose.
    - [Mosquitto MQTT](https://mosquitto.org/). An open-source MQTT broker.
- [Arduino IDE](https://www.arduino.cc/en/software). Is an Integrated Developement Environmet to load software to Arduino and Arduino-based boards.
    - [Espressif ESP32 boards for Arduino](https://github.com/espressif/arduino-esp32). Boards library for ESP32 micro controllers in Arduino.
    - [libfuse2](https://software.opensuse.org/package/libfuse2). A Linux Kernel interface.
    - [Git](https://git-scm.com/). Version control software.
    - [arp-Scan](https://linux.die.net/man/1/arp-scan). Network analyzer.
    - [net-tools](https://net-tools.sourceforge.io/). A collection of networking utilities.
- [Python 3](https://www.python.org/). A high-level programming language.
    - [PIP](https://pypi.org/project/pip/). Python package manager.
        - [deepface](https://github.com/serengil/deepface). Facial processing python library.
        - [paho-mqtt](https://pypi.org/project/paho-mqtt/). An M2M protocol library.
        - [OpenCV](https://opencv.org/). OpenCV provides a real-time optimized Computer Vision library.
- [NodeJS](https://nodejs.org/en). An open-source, cross-platform JavaScript runtime environment..
    - [Node-Red](https://nodered.org/). A programming tool for wiring together hardware devices, APIs and online services in new and interesting ways.
        - [node-red-dashboard](https://flows.nodered.org/node/node-red-dashboard). This module provides a set of nodes in Node-RED to quickly create a live data dashboard. 

### Hardware

Suggested minimum requirements are listed.

- Intel Core i5 8th generation or better.
- AMD Ryzen 5 3rd generation or better.
- Virtualization compatible processor.
- 8GB RAM or better.
- nVidia GTX 1060 or better.

Testing was performed in a system with following capabilities:

![](https://github.com/hugoescalpelo/data-visualization/blob/main/Images/Screenshot%20from%202023-10-12%2016-17-54.png?raw=true)

**Other hardware**
- [ESP32CAM with base](https://docs.ai-thinker.com/en/esp32-cam). ESP32 based developement board with camera.
- [FTDI232](https://ftdichip.com/) (optional). Serial converter. 

## Installation instructions

Once an Ubuntu system is set, follow this steps. Linked documentation includes details about requirements for each step.

1. Set up GPU. [Details](https://github.com/hugoescalpelo/data-visualization/blob/main/CUDA/cuda-toolkit-instructons.md)
2. Install Docker Engine. [Details](https://github.com/hugoescalpelo/data-visualization/blob/main/Docker/docker-documentation.md)
3. Enable GPU Access to containers. [Details](https://github.com/hugoescalpelo/data-visualization/blob/main/Docker/docker-gpu-documentation.md)
4. Set the Docker Compose file. This step will install CodeProject.AI Server, mosquitto and MySQL Server. [Details](https://github.com/hugoescalpelo/data-visualization/blob/main/Docker/docker-compose-documentation.md)
5. Configure CodeProject.AI Server for OCR. [Details](https://github.com/hugoescalpelo/data-visualization/blob/main/CodeProject.AI/ocr-settings.md)
6. Program the IP camera. [Details](https://github.com/hugoescalpelo/data-visualization/blob/main/ESP32CAM/video-server-documentation.md)
7. Set up deepface. [Details](https://github.com/hugoescalpelo/data-visualization/blob/main/deepface/deepface-documentation.md).
8. Install and configure Node-Red. [Details](https://github.com/hugoescalpelo/data-visualization/blob/main/NodeRed/node-red-documentation.md)
 

## Testing
I also provide testing instuctions as part of my archive process.

- [CodeProject.AI Server basic tests](https://github.com/hugoescalpelo/data-visualization/blob/main/CodeProject.AI/basic-testing.md)
- [Deepface basic tests](https://github.com/hugoescalpelo/data-visualization/blob/main/deepface/deepface-documentation.md   )

You can also test the API for **CodeProject.AI Server**. You will need to install Postman, chech the [instructions here](https://github.com/hugoescalpelo/data-visualization/blob/main/Postman/postman-documentation.md).

- [Face Detection](https://github.com/hugoescalpelo/data-visualization/blob/main/CodeProject.AI/face-detection.md)
- [Face Register](https://github.com/hugoescalpelo/data-visualization/blob/main/CodeProject.AI/register-testing.md)
- [Face Recognition](https://github.com/hugoescalpelo/data-visualization/blob/main/CodeProject.AI/face-recognition.md)
- [OCR]()

## Launching instructions

To launch this App, you need the following:

1. Launch Docker. Provided instructions set Docker to launch at login. Nothing is required. You chan check that mosquitto and CodeProject.AI Server are running with following command.
    ```
    sudo docker ps -a
    ```
    If containers are not running, start them up with following command.
    ```
    docker start $(docker ps -a -q)
    ```
2. Energize the ESP32CAM
3. Run Node-Red with ```node-red```
4. Open [localhost:1880/ui](http://localhost:1880/ui)

## Operation Instructions
1. Clic on capture button to run the facial recognition.

Note: OCR works automatically

You will see something similar to the first image of this document.

## Reference

- [Notes on CUDA nVidia support - CodeProject.AI docs](https://www.codeproject.com/Articles/5322557/CodeProject-AI-Server-AI-the-easy-way)
- [CUDA Installation guide](https://gist.github.com/denguir/b21aa66ae7fb1089655dd9de8351a202)
- [cuDNN archive](https://developer.nvidia.com/rdp/cudnn-archive)
- [Install CodeProject.AI with GPU](https://youtu.be/6_jZmAt2yV4?si=QbV8ph1Ldi7IBFY6)
- [What does off means in nvidia-smi](https://forums.developer.nvidia.com/t/what-does-off-mean-in-the-output-of-nvidia-smi/37509/3)
- [GPU Persistance Mode](https://www.microway.com/hpc-tech-tips/nvidia-smi_control-your-gpus/)




