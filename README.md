# Deploying GPT-J with DeepSpeed on AWS Sagemaker

This repository demonstrates how you can accelerate GPT-J with DeepSpeed Inference and deploy it on AWS SageMaker.

## LLM Sizes Grow Exponentially  

<img src="img/ZERO-1.png" alt="Alt text for the image" width="1000"/>


<img src="img/ZERO-2.png" alt="Alt text for the image" width="1000"/>

In data parallelism, each GPU holds a full copy of the model, and the data is split across GPUs. This approach becomes memory-intensive as the model size grows, as every model replica requires its own memory for parameters, gradients, and optimizer states. <br>

ZeRO optimizes memory usage in a data-parallel setting by partitioning the states of the optimizer, gradients, and parameters across the GPUs. This partitioning allows for significantly larger models to be trained, as no single GPU holds the entire model state, thus alleviating the memory bottleneck.


<img src="img/ZERO-3.png" alt="Alt text for the image" width="1000"/>

Model parallelism, on the other hand, involves splitting the model's layers across different devices, so each device is responsible for computing a part of the forward and backward passes of the neural network. This is different from data parallelism and is typically used when a model's layers are too large to fit into a single GPU's memory. <br>

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
