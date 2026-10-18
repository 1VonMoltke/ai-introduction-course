---
title: Assignment-3：DDPM 与 DDIM
summary: 在二维 Swiss-roll 数据集上实现噪声预测网络、DDPM 和 DDIM，并比较两种采样方法。
order: 23
updated: 2026-10-18
points: 100
status: 待公布
zipUrl: files/packages/assignment3.zip
zipLabel: 实验代码下载
---

# Assignment-3：DDPM 与 DDIM

本次作业使用二维 Swiss-roll 数据集，先训练噪声预测网络，再分别用 DDPM 和 DDIM 生成样本。下载上方实验代码包，打开其中的 `DDPM_DDIM.ipynb`，按 notebook 内的说明完成标有 `TODO` 的部分。

## 截止时间

Soft DDL 与 Hard DDL 待课程组公布。

## 环境设置

本实验需要可用的 PyTorch GPU 环境。可以使用 Colab、Kaggle GPU，或本地 CUDA GPU。在 Colab 中上传 notebook 后选择 GPU 运行时；本地运行可安装压缩包中的 `requirements.txt`，并确认 `torch.cuda.is_available()` 返回 `True`。

## 实验内容

1. **噪声预测网络**：按指定维度连接 `TimeLinear` 层，并在最后一层以外使用 ReLU。
2. **DDPM**：完成噪声调度器、前向加噪、逐步反向采样和噪声预测损失；训练 5000 次迭代后绘制损失曲线。
3. **DDIM**：复用训练好的噪声预测网络，实现 DDIM 单步与完整采样过程。
4. **结果比较**：展示两种方法生成的样本，并记录各自与目标分布的 Chamfer Distance。

原实验的参考目标是 DDPM 的 Chamfer Distance 低于 **20**、DDIM 低于 **40**。本课程总分为 100 分，具体评分细则待课程组公布。

## 报告与提交文件

报告中简要说明实现过程，并附上损失曲线、DDPM 和 DDIM 的 Chamfer Distance 及采样可视化，分析两种采样方法的差异。提交前从头运行 notebook，保留运行输出。建议按以下结构整理，压缩包命名为 `学号_assignment3.zip`：

```text
assignment3/
├── DDPM_DDIM.ipynb
└── 学号_report.pdf
```

将压缩文件提交至[课程网盘](https://box.nju.edu.cn/u/d/a927a77a89fc41b5830d/)。

## 成绩查询

[查询个人成绩](https://table.nju.edu.cn/dtable/links/558f7648778c4a34bc77)

## 提醒

- 只在 notebook 的 `TODO` 区域填写答案，提交前从头运行并保留输出。
- 不要把个人答案上传到公开仓库。
- 作业模板改编自 [KAIST CS492(C) Fall 2025 Programming Assignment 1](https://github.com/KAIST-Visual-AI-Group/Diffusion-2025-Assignment1-DDPM-DDIM)，原作者信息保留在 notebook 中。
