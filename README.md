# Learning Loss for Active Learning, with a focus on learning rates!
Reproducing experimental results of LL4AL [Yoo et al. 2019 CVPR]
This work is based the [ori ginal reproduce repo](https://github.com/Mephisto405/Learning-Loss-for-Active-Learning).

# What is changed?
* We changed the code to enable using config files [like this one](https://github.com/anonymous-ml-enjoyer/ll4al-reproduce-lr/blob/main/configs/cifar10_resnet18.yaml), so that managing different hyperparameters would be easier!
* We added a new set of models, [WideResNets](https://github.com/anonymous-ml-enjoyer/ll4al-reproduce-lr/blob/main/models/wide_resnet.py) that can be configured through the input config to the code!
* We added the ability to use [OneCycleLR](https://pytorch.org/docs/stable/generated/torch.optim.lr_scheduler.OneCycleLR.html) as the learning rate scheduler if one wants to!
* We added the SVHN dataset.

# Run

To use the code, simply create your own config file, or use one of the provided config files (we assume using (the config indicating CIFAR10 dataset with ResNet18 model)[https://github.com/anonymous-ml-enjoyer/ll4al-reproduce-lr/blob/main/configs/cifar10_resnet18.yaml]), and run:
```python
python main.py --config_path=configs/cifar10_resnet18.yaml --save_dir=.
```

# Results

| **Dataset** | **Model**      | **Learning Rates**                   | **Plot**                                                   |
|-------------|----------------|--------------------------------------|------------------------------------------------------------|
| CIFAR10     | ResNet18       | .1, .2, .25, .3, .35, .4. .5, 1., 2. | https://chart-studio.plotly.com/~anonymous.ml.enjoyer/1/#/ |
| CIFAR10     | WideResNet 1BL | .1, .2, .3, .5, 1., 2.               | https://chart-studio.plotly.com/~anonymous.ml.enjoyer/11/  |
| SVHN        | ResNet18       | .1, .2, .3, .5, 1., 2.               | https://chart-studio.plotly.com/~anonymous.ml.enjoyer/7    |
| SVHN        | WideResNet 1BL | .1, .2, .3, .5, 1., 2.               | https://chart-studio.plotly.com/~anonymous.ml.enjoyer/9/#/ |


# Requirements
 torch >= 1.1.0

 numpy >= 1.16.2

 tqdm >= 4.31.1
