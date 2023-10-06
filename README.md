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

## Quirks and features

This app is developed considering the following:
- **Variety**: Demonstrate multiple paradigms and programming languages usage.
- **Robustness**: modularity and interoperability.
- **Reproducibility**: easy installation and configuration in multiple devices.
- **Scalability**: multiple instances of this app can be runned in same device or many devices.
- **Mantainability**: detailed documentation and version control.
- **Openness**: all tools are well known and maintainded open source projects.

## Requirements

To run this app you'll need the following:

- [Ubuntu 22.04LTS](https://ubuntu.com/download/desktop). Also can be runned in any Debain Based distro, VM or WSL system.
- [CUDA Toolkit](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=22.04&target_type=deb_local). This allows to use CodeProject.AI with GPU
- [CodeProject.AI](https://hub.docker.com/r/codeproject/ai-server). This is an AI server for image recognition and will be installed via Docker Compose.
- [Docker Engine](https://docs.docker.com/engine/install/ubuntu/). This allow to install with all dependencies provided by publisher.
- An nVidia graphics card.


## Instructions

Once an Ubuntu system is set, follow this steps. Linked documentation includes details about requirements for each step.

1. Install docker. [Instructions](https://github.com/hugoescalpelo/data-visualization/blob/main/Docker/docker-documentation.md)
2. Install CUDA Toolkit. [Instructions]()
3. Set the Docker Compose file. [Instructions]()



<!-- 
2. Create the needed directories
3. Install compose
4. Move the configuration files
5. Set up nodeRed
6. Setup  -->


