# Local-Erase-Vectors
Lean and Green: Efficient Machine Unlearning in Industrial IoT via Local Erase Vectors

本项目为基于CIFAR10和ResNet18的Local Erase Vector (LEV) 机器遗忘算法最小可运行演示。

## 依赖安装

建议使用Python 3.8+，并提前安装CUDA驱动（如有GPU）。

## 算法简介

- 预训练ResNet18模型于CIFAR10全数据集。
- 选择一个类别（如airplane）作为遗忘目标。
- 针对该类别样本，生成最大化损失的对抗扰动（LEV），并用模型自身预测结果作为新标签。
- 用这些对抗样本微调模型，削弱其对遗忘类别的识别能力。
- 最后用保留集低学习率微调，恢复泛化。

## 输出

输出遗忘类、保留类和测试集的准确率，便于评估遗忘效果。
输出LEV前后forget class的聚类对比
