# ORTModule Bug Bash instructions

## Prerequisites

* A machine with at least one GPU
* Docker
* PyTorch training script

## Setup

* Download a dockerfile

  e.g. `wget https://raw.githubusercontent.com/pytorch/ort/main/docker/Dockerfile.ort-cu111-cudnn8-devel-ubuntu18.04`
  
* Build a docker image

  e.g. `docker build -f Dockerfile.ort-cu111-cudnn8-devel-ubuntu18.04 -t ort.cu111 .`
  
  
## Add ORTModule to your training script

* Download your training script

  e.g. `wget https://raw.githubusercontent.com/pytorch/ort/main/tests/bert_for_sequence_classification.py`
  
* Import ORTModule 

  e.g. `https://github.com/pytorch/ort/blob/main/tests/bert_for_sequence_classification.py#L19`
  
* Wrap your model in ORTModule

  e.g. `https://github.com/pytorch/ort/blob/main/tests/bert_for_sequence_classification.py#L378`

## Run

* Run the container

  e.g. `docker run -it --gpus all --name my-experiments ort.cu111:latest`
  
* Install any dependencies of your training script

  e.g. `pip install wget pandas sklearn transformers`
  
* Run the training script

  e.g. `python bert_for_sequence_classification.py`
