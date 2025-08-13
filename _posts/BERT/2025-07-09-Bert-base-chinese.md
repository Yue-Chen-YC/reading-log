---
tags  : [Model, BERT]
category: [Mandarin, BERT]
---
## Bert: Pre-training of deep bidirectional transformers for language understanding (Devlin et al., 2019)

## Citation 
Devlin, J., Chang, M. W., Lee, K., & Toutanova, K. (2019, June). Bert: Pre-training of deep bidirectional transformers for language understanding. In Proceedings of the 2019 conference of the North American chapter of the association for computational linguistics: human language technologies, volume 1 (long and short papers) (pp. 4171-4186).

## My thoughts

## Transformer 
- 依赖于 **注意力机制 (self-attention = 缩放点积注意力机制)**
  - **formula **: Attention(Q, K, V) = softmax((QKᵀ) / √dₖ) V 
  - 输入句的每个词转化成对应的词嵌入向量 （词的特征向量）
  - 输入 （vector x） = 句子的长度 * 词嵌入向量的维度
  - 权重vector，wq，wk，wv （初始值是随机的，最优值需要通过训练获得），vector x * vector，wq，wk，wv = query （vector q），key （vector k），value （vector v）
  - query （vector q），key （vector k），value （vector v）
  - 计算一个词的特征值，self-attention会使该词与给定句子中的所有词联系起来

**计算步骤**
  1. 计算vector q and vecotr k的点积 （q * k），计算两个向量的点积可以知道它们之间的相似度 （点积越大，相似度越多）
  2. 计算q * k / 键向量的维度的平方根 = 获得稳定的梯度
  3. softmax进行归一化处理 （每个词和所有词的相关程度）
  4. 计算注意力vector z （再乘以vector v），注意力vector z = 值向量与分数加权之后求和所得的结果
- 两个部分组成
  - **encoder** = 主要功能是提取原句中的特征，（一组N个编码器串联而成，特征会成最后一个编码器输出）
    - 编码器：多头注意力层 -> 前馈网络层
      - **多头注意力层**
        - 使用多个注意力vector，而不是单一的vector，可以提高注意力的准确度
        - multi-head attention = concatenate(z1, z2, z3 ...)w0
      -  **positional encoding (word order)**
        - 位置编码vector (p) 添加到输入vector x （vector x + vector p）
        - 使用cosin/sin来计算位置编码
          - P (pos, 2i) = sin (pos / 10000^2i/dmost) = 如果i是偶数
          - P (pos, 2i + 1) = cosin (pos / 10000^2i/dmost) = 如果i是奇数
            - pos = 词在句子中的位置，i表示输入vector中的位置
        - **前馈网络层**
          - 两个有ReLU激活函数的全连接层 （ReLU 通常能够比 sigmoid 和 tanh 更快地收敛，因为它避免了梯度消失（负值直接变为 0，不会压缩输出））
          - 叠加和归一组件 （残差链接与层的归一化）
<img width="1190" height="1024" alt="image" src="https://github.com/user-attachments/assets/74a779bc-f387-4f7a-9f0d-8346fc05cda1" />

  - **decorder**
    - 预测词汇的概率分布，并选择概率最高的词作为输出 
- 工作原理：向encoder输入一句话（原句），让其学习这句话的特征，再把特征作为输入给decorder，decorder会生成输出句（目标句）
<img width="355" height="523" alt="image" src="https://github.com/user-attachments/assets/34baee1b-5298-4bcf-90f6-e37c51200d8b" />

## BERT
BERT（Bidirectional Encoder Representations from Transformers）是一个通用的预训练语言模型，旨在通过双向Transformer架构，生成深层的上下文语言表示。它的核心创新在于双向预训练（bidirectional pre-training）和微调（fine-tuning方法，使其能够在广泛的自然语言处理（NLP）任务中实现卓越表现。
- designed for pretraining deep bidirectional representations from unlabeled text by jointly conditioning on both left and right context in all layers
- can be fine-tuned with just one additional output layer to create state-of-the-art models for a wide range of tasks, such as question answering and language inference
- logit是bert在softmax之前输出的概率分布

## BERT 的核心架构
BERT 的架构基于 Transformer 编码器（Encoder， 只有encoder的transformer），具体如下：

- **多层双向 Transformer**：
  - 可以从两个方向读取一个句子，学习单词之间的关系和语境含义，再将其特征作为输出
- BERT 使用了 Transformer 编码器架构（Vaswani et al. 提出），通过自注意力机制（Self-Attention）捕捉句子中所有单词的全局上下文。
  - BERT 的模型分为两种规模：
    - BERT-Base：12 层 Transformer，768 维隐藏层，12 个注意力头，总参数量约 1.1 亿。
    - BERT-Large：24 层 Transformer，1024 维隐藏层，16 个注意力头，总参数量约 3.4 亿。

- 双向特性：
  - 与单向语言模型（例如 GPT）不同，BERT 是深度双向的，即它能同时利用左侧和右侧的上下文信息来生成表示。
  - 例如，对于句子“我喜欢[MASK]苹果”，BERT 可以同时利用“我喜欢”和“苹果”来预测被掩码的词。

## BERT 的输入表示
BERT 的输入使用了一个统一的表示方法，能够适应单句任务和句子对任务。输入包含以下三种嵌入信息 （标记，分段，位置）：

## 标记嵌入：

[CLS]：表示分类任务的全局句子表示。
[SEP]：用于分隔句子或句子片段。

## Segment Embedding 分段嵌入：
- 区分两个给定的句子，句子a，句子b
- 用于区分两个句子（或片段）。
- 例如，对于句子对任务，句子 A 的所有 Token 嵌入加上 Segment A 的嵌入，句子 B 加上 Segment B 的嵌入。

## Position Embedding 位置嵌入：
- transformer没有循环机制，以并行方式处理所有的词，所以需要word order information
- 单词标记的word order
- 用于表示每个 Token 在句子中的位置，帮助模型捕捉顺序信息。
输入格式：

单句任务：[CLS] 句子 [SEP]
句子对任务：[CLS] 句子 A [SEP] 句子 B [SEP]


## WordPiece 词元分析器，Token Embedding（词嵌入）：

- 使用 WordPiece 分词将句子分割为子词单元（如“playing” → ["play", "##ing"]）。
- 每个子词被映射到一个固定维度的嵌入向量。
- 处理 out-of- vocabulary word是有效的


## BERT 的预训练任务
BERT 的创新点之一是它设计了两个预训练任务，帮助模型学习通用的语言表示：
- BERT 是自动编码式语言模型，从两个方向阅读句子，然后进行预测

## Masked Language Model (MLM) 掩码语言模型构建 or 完形填空任务
- 目标：让模型预测被随机掩码的单词。
- 机制 （80 - 10 - 10 规则）：
  - 随机掩码输入序列中 15% 的 Token。
  - 对被选中的 Token：
    - 80% 的概率替换为 [MASK]；
    - 10% 的概率替换为一个随机 Token 来替换实际词；
    - 10% 的概率保持不变。
- 模型需要通过上下文信息预测被掩码的词。

例子：
输入：“我喜欢[MASK]苹果。”
模型任务：预测 [MASK] 为“吃”。

## 优势：
双向上下文：MLM 允许模型同时利用左侧和右侧的上下文信息，生成深度双向表示。

## whole word masking 全词掩码
- 如果子词被掩盖，子词对应的单词也会被掩盖

## Next Sentence Prediction (NSP) binary task
- 目标：让模型理解句子之间的逻辑关系。
- 机制 （需要各占50%）：
- 从语料库中随机采样两段文本 A 和 B：
  - 50% 的概率 B 是 A 的下一句。
  - 50% 的概率 B 是从语料中随机抽取的句子。
  - 模型需要判断 B 是否是 A 的下一句。

- 例子：
  - 输入 1（正样本）：[CLS] 我喜欢苹果 [SEP] 它们很甜 [SEP]
  - 输入 2（负样本）：[CLS] 我喜欢苹果 [SEP] 昨天天气很好 [SEP]
  - 模型任务：预测“是否为下一句”。

## 优势：
NSP 提升了模型对句子对任务（如问答和自然语言推理）的理解能力。

## BERT 的微调机制
- 在完成预训练后，BERT 可以通过微调（Fine-Tuning）适配各种下游任务：

- 加载预训练模型：将预训练的权重作为初始化参数。
- 添加任务特定的输出层：

  - 分类任务：在 [CLS] 向量后添加一个全连接层。
  - 序列标注任务：对每个 Token 的隐藏向量添加标注层。
  - 阅读理解任务：预测答案的起始和结束位置。
  - 端到端训练：利用任务标注数据，微调所有参数以适配具体任务。

## 优点：

- 统一框架：BERT 的预训练模型可以适配多种任务，仅需添加少量任务特定参数。
- 数据高效：即使在小数据集上，微调也能取得良好效果。
