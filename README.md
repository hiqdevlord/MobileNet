# MobileNet

A tensorflow implementation of Google's [MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications](https://arxiv.org/abs/1704.04861)

## Base Module

<div align="center">
<img src="https://github.com/Zehaos/MobileNet/blob/master/figures/dwl_pwl.png"><br><br>
</div>

## Accuracy on ImageNet-2012 Validation Set

| Model | Width Multiplier |Preprocessing  | Accuracy-Top1|Accuracy-Top5 |
|--------|:---------:|:------:|:------:|:------:|
| [MobileNet](https://pan.baidu.com/s/1b9OmHS) |1.0| Same as Inception | 66.51% | 87.09% |

**Loss**
<div align="center">
<img src="https://github.com/Zehaos/MobileNet/blob/master/figures/epoch90_full_preprocess.png"><br><br>
</div>

## Usage

### First

Prepare imagenet data.

Please refer to Google's tutorial for [training inception](https://github.com/tensorflow/models/tree/master/inception#getting-started).

### Second

Modify './script/train_mobilenet_on_imagenet.sh' according to your environment.

```
bash ./script/train_mobilenet_on_imagenet.sh
```

## Trouble Shooting

1. About the MobileNet model size

According to the paper, MobileNet has 3.3 Million Parameters, which does not vary based on the input resolution. It means that the number of final model parameters should be larger than 3.3 Million, because of the fc layer.

When using RMSprop training strategy, the checkpoint file size should be almost 3 times as large as the model size, because of some auxiliary parameters used in RMSprop. You can use the inspect_checkpoint.py to figure it out.

2. Pretrained weight

Welcome to share if you had trained a better model.

## TODO
- [x] Train on Imagenet
- [x] Add Width Multiplier Hyperparameters
- [x] Report training result
- [ ] Intergrate into object detection task

## Reference
[MobileNets: Efficient Convolutional Neural Networks for Mobile Vision Applications](https://arxiv.org/abs/1704.04861)

[SSD-Tensorflow](https://github.com/balancap/SSD-Tensorflow)
