---
title: 深度学习
type: docs
---

## 术语
- 模型(Model)的功能形式称为其架构(architecture)
- 权重(weights)称为参数(parameters)
- 预测(predictions)是根据自变量计算的，自变量是不包括标签(labels)的数据
- 模型的结果称为预测。
- 性能的衡量标准称为损失(loss)。
- 损失不仅取决于预测，还取决于正确的标签（也称为目标或因变量）；例如，“狗”或“猫”。

```
for{
    predictions=architecture(inputs,parameters)
    parameters=loss(predictions,labels)
}
```
- 没有数据就无法创建模型。
- 模型可以学习仅对用于训练它的输入数据中看到的模式进行操作。
- 这种学习方法仅创建预测，而不创建建议的actions。
- 仅仅有输入数据的示例是不够的；我们还需要这些数据的标签（例如，狗和猫的图片不足以训练模型；我们需要为每个数据添加一个标签，说明哪些是狗，哪些是猫）。

## 过度拟合
over-fitting
> 如果你训练足够大的模型足够长的时间，它最终会记住数据集中每个项目的标签！结果不会是一个有用的模型，因为我们关心的是我们的模型在以前未见过的图像上的表现如何。这始终是我们创建模型时的目标：让它对模型训练后仅在未来看到的数据有用。

> 即使您的模型没有完全记住所有数据，在训练的早期，它也可能已经记住了其中的某些部分。因此，你训练的时间越长，你的准确性就越高.
> 您在训练集上的准确性就越高；验证集的准确性也会暂时提高，但最终会开始变得更糟，因为模型开始记住训练集而不是在数据中寻找可概括的基础模式。当这种情况发生时，我们说
> 模型过度拟合

## 卷积神经网络
CNN 创建计算机视觉模型.他们的结构受到人类视觉系统工作原理的启发。

## ResNet
resnet34,34 代表网络中包含 34 个可训练层.

层数越多，神经网络的拟合能力越强，可以学习到更复杂的特征。但是，层数越多也容易导致过拟合问题，同时也会增加训练难度，使模型难以收敛。

层数越少，神经网络的拟合能力越弱，可能无法学习到足够的特征。但是，层数越少也越不容易过拟合，训练难度也越小。

**过拟合**是指模型在训练集上表现良好，但在测试集上表现较差.

**欠拟合**是指模型在**训练集**和**测试集**上都表现不佳.

## metric
指标

- error_rate 错误率
- accuracy  准备率;accuracy= 1-error_rate;accuracy + error_rate = 1

## loss
损失 定义训练系统可以用来自动更新权重的"性能衡量标准"

## 预训练模型
使用预训练模型时,**删除最后一层**,因为它始终是针对原始模型专门定制的.
并将其替换为具有随机权重的一个或多个新层,其大小适合我们正在使用的数据集.
模型的最后一部分称为**头部**.

将预训练模型用于不同于最初训练目的的任务称为**迁移学习**.

## epochs
epoch表示将整个训练集通过一次的学习过程.

## fine-tuning
微调
一种迁移学习技术，通过使用与预训练不同的任务进行额外的训练来更新预训练模型的参数。

