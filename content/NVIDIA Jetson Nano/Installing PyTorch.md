### Method 1

The best instructions are actually provided by the Ultralytics team as part of their installation process. Thank you
Ultralytics for building PyTorch & Torchvision for the Jetson!

See [https://docs.ultralytics.com/guides/nvidia-jetson/#install-pytorch-and-torchvision)](https://docs.ultralytics.com/guides/nvidia-jetson/#install-pytorch-and-torchvision)


### Method 2

> [!warning]
> The instructions below were the first way that I managed to install PyTorch/Torchvision successfully, but I wouldn't
recommend them anymore.

#### PyTorch

Follow the instructions [here](https://docs.nvidia.com/deeplearning/frameworks/install-pytorch-jetson-platform/index.html) to install `cusparselt`. Then find the appropiate PyTorch URL using [this index](https://developer.download.nvidia.com/compute/redist/jp/). Continue with the instructions after downloading the python wheel.

#### Torchvision

This one is quite straightforward. Clone the repository and switch to the appropiate version tag. For example `git checkout v0.20.0` . Find the appropiate version using the matrix on the repo:
![[Pasted image 20250124160715.png]]

Then, follow [the build instructions](https://github.com/pytorch/vision/blob/main/CONTRIBUTING.md#development-installation).
