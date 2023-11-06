# Deploying GPT-J with DeepSpeed on AWS Sagemaker

This repository demonstrates how you can accelerate GPT-J with DeepSpeed Inference and deploy it on AWS SageMaker.

## LLM Sizes Grow Exponentially  

<img src="img/ZERO-1.png" alt="Alt text for the image" width="1000"/>

In data parallelism, each GPU holds a full copy of the model, and the data is split across GPUs. This approach becomes memory-intensive as the model size grows, as every model replica requires its own memory for parameters, gradients, and optimizer states. <br>

ZeRO optimizes memory usage in a data-parallel setting by partitioning the states of the optimizer, gradients, and parameters across the GPUs. This partitioning allows for significantly larger models to be trained, as no single GPU holds the entire model state, thus alleviating the memory bottleneck.

<img src="img/ZERO-2.png" alt="Alt text for the image" width="1000"/>
<img src="img/ZERO-3.png" alt="Alt text for the image" width="1000"/>
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
