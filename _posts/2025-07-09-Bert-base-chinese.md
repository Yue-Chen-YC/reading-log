---
tags  : [Model, BERT]
category: [Mandarin, BERT]
---
## Bert: Pre-training of deep bidirectional transformers for language understanding (Devlin et al., 2019)

## Citation 
Devlin, J., Chang, M. W., Lee, K., & Toutanova, K. (2019, June). Bert: Pre-training of deep bidirectional transformers for language understanding. In Proceedings of the 2019 conference of the North American chapter of the association for computational linguistics: human language technologies, volume 1 (long and short papers) (pp. 4171-4186).

## My thoughts


## BERT
BERT（Bidirectional Encoder Representations from Transformers）是一个通用的预训练语言模型，旨在通过双向Transformer架构，生成深层的上下文语言表示。它的核心创新在于双向预训练（bidirectional pre-training）和微调（fine-tuning方法，使其能够在广泛的自然语言处理（NLP）任务中实现卓越表现。
- designed for pretraining deep bidirectional representations from unlabeled text by jointly conditioning on both left and right context in all layers
- can be fine-tuned with just one additional output layer to create state-of-the-art models for a wide range of tasks, such as question answering and language inference

## BERT 的核心架构
BERT 的架构基于 Transformer 编码器（Encoder），具体如下：

- 多层双向 Transformer：

BERT 使用了 Transformer 编码器架构（Vaswani et al. 提出），通过自注意力机制（Self-Attention）捕捉句子中所有单词的全局上下文。
BERT 的模型分为两种规模：
BERT-Base：12 层 Transformer，768 维隐藏层，12 个注意力头，总参数量约 1.1 亿。
BERT-Large：24 层 Transformer，1024 维隐藏层，16 个注意力头，总参数量约 3.4 亿。

- 双向特性：

与单向语言模型（例如 GPT）不同，BERT 是深度双向的，即它能同时利用左侧和右侧的上下文信息来生成表示。
例如，对于句子“我喜欢[MASK]苹果”，BERT 可以同时利用“我喜欢”和“苹果”来预测被掩码的词。

## BERT 的输入表示
BERT 的输入使用了一个统一的表示方法，能够适应单句任务和句子对任务。输入包含以下三种嵌入信息：

## Token Embedding（词嵌入）：

使用 WordPiece 分词将句子分割为子词单元（如“playing” → ["play", "##ing"]）。
每个子词被映射到一个固定维度的嵌入向量。

## Segment Embedding（片段嵌入）：

用于区分两个句子（或片段）。

例如，对于句子对任务，句子 A 的所有 Token 嵌入加上 Segment A 的嵌入，句子 B 加上 Segment B 的嵌入。
Position Embedding（位置嵌入）：

用于表示每个 Token 在句子中的位置，帮助模型捕捉顺序信息。
输入格式：

单句任务：[CLS] 句子 [SEP]
句子对任务：[CLS] 句子 A [SEP] 句子 B [SEP]

## 特殊标记：

[CLS]：表示分类任务的全局句子表示。
[SEP]：用于分隔句子或句子片段。

## BERT 的预训练任务
BERT 的创新点之一是它设计了两个预训练任务，帮助模型学习通用的语言表示：

## Masked Language Model (MLM)
目标：让模型预测被随机掩码的单词。
机制：
随机掩码输入序列中 15% 的 Token。
对被选中的 Token：
- 80% 的概率替换为 [MASK]；
- 10% 的概率替换为一个随机 Token；
- 10% 的概率保持不变。
模型需要通过上下文信息预测被掩码的词。

例子：
输入：“我喜欢[MASK]苹果。”
模型任务：预测 [MASK] 为“吃”。

## 优势：
双向上下文：MLM 允许模型同时利用左侧和右侧的上下文信息，生成深度双向表示。

## Next Sentence Prediction (NSP)
目标：让模型理解句子之间的逻辑关系。
机制：
从语料库中随机采样两段文本 A 和 B：
- 50% 的概率 B 是 A 的下一句。
- 50% 的概率 B 是从语料中随机抽取的句子。
模型需要判断 B 是否是 A 的下一句。

例子：
输入 1（正样本）：[CLS] 我喜欢苹果 [SEP] 它们很甜 [SEP]
输入 2（负样本）：[CLS] 我喜欢苹果 [SEP] 昨天天气很好 [SEP]
模型任务：预测“是否为下一句”。

## 优势：
NSP 提升了模型对句子对任务（如问答和自然语言推理）的理解能力。

## BERT 的微调机制
在完成预训练后，BERT 可以通过微调（Fine-Tuning）适配各种下游任务：

加载预训练模型：将预训练的权重作为初始化参数。
添加任务特定的输出层：

- 分类任务：在 [CLS] 向量后添加一个全连接层。
- 序列标注任务：对每个 Token 的隐藏向量添加标注层。
- 阅读理解任务：预测答案的起始和结束位置。
- 端到端训练：利用任务标注数据，微调所有参数以适配具体任务。

## 优点：

统一框架：BERT 的预训练模型可以适配多种任务，仅需添加少量任务特定参数。
数据高效：即使在小数据集上，微调也能取得良好效果。
