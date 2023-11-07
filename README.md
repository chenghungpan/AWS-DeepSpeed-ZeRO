# Deploying GPT-J with DeepSpeed on AWS Sagemaker

This repository demonstrates how you can accelerate GPT-J with DeepSpeed Inference and deploy it on AWS SageMaker.

## LLM Sizes Grow Exponentially  

<img src="img/ZERO-1.png" alt="Alt text for the image" width="1000"/>

As we enter the era of LLMs with billions, or even trillions of parameters, traditional training methodologies falter. These expansive neural networks demand extraordinary computational resources—far beyond the capabilities of any single machine. This is where distributed training paradigms, and specifically, tools like DeepSpeed come into play.

## Why DeepSpeed?

DeepSpeed is a deep learning optimization library that provides a suite of tools designed to facilitate the training of very large models. It extends PyTorch with capabilities that efficiently leverage hardware at scale, optimizing both memory usage and speed to break through previous limitations.

Here's why the advent of DeepSpeed is pivotal for LLMs:

### 1. Scalability: 
LLMs require a vast canvas upon which their myriad parameters can interact. DeepSpeed orchestrates training across multiple GPUs and nodes, breaking the barriers of single-device memory limits and allowing these colossal models to scale gracefully.

### 2. Speed: 
Time is of the essence in machine learning. DeepSpeed employs strategies like tensor slicing to maximize parallelism and throughput, significantly reducing the clock time needed for model training iterations.

### 3. Memory Optimization: 
Through innovative techniques like ZeRO (Zero Redundancy Optimizer) and offloading, DeepSpeed minimizes memory footprint, enabling training of models that were previously infeasible due to hardware constraints.

### 4. Cost-Effectiveness: 
By improving resource utilization and reducing computational overhead, DeepSpeed makes the training of LLMs more economically viable, democratizing access to state-of-the-art models.

### 5. Flexibility and Accessibility: 
DeepSpeed's compatibility with PyTorch means that it can be integrated into existing workflows with minimal friction, lowering the barrier to entry for practitioners and researchers alike.



<img src="img/ZERO-2.png" alt="Alt text for the image" width="1000"/>

### Data Parallelism
In data parallelism, each GPU holds a full copy of the model, and the data is split across GPUs. This approach becomes memory-intensive as the model size grows, as every model replica requires its own memory for parameters, gradients, and optimizer states. <br>


<img src="img/ZERO-3.png" alt="Alt text for the image" width="1000"/>

### Model Parallelism
Model parallelism involves splitting the model's layers across different devices, so each device is responsible for computing a part of the forward and backward passes of the neural network. This is different from data parallelism and is typically used when a model's layers are too large to fit into a single GPU's memory. <br>

ZeRO's techniques reduce the redundancies in data parallelism by cleverly distributing model states across the GPUs, while also incorporating aspects of model parallelism by allowing for the training of models where individual layers may be too large for a single device. Thus, while ZeRO primarily optimizes data parallel training, its state partitioning allows for training models of a size that would traditionally require model parallelism, effectively giving practitioners the best of both worlds in certain scenarios.

<img src="img/ZERO-4.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-5.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-6.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-7.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-8.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-9.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-10.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-11.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-12.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-13.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-14.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-15.png" alt="Alt text for the image" width="1000"/>
