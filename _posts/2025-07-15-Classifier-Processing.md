---
tags  : [Classifier, Processing]
category: [Mandarin, Classifier, Cue-based retrieval]
---
## Similarity-Based Interference in the Processing of Classifier-Noun Dependencies in Mandarin Chinese (Hao et al., 2024)

## Citation 
Hao, H., Fuchs, Z., & Vasishth, S. (2024). Similarity-Based Interference in the Processing of Classifier-Noun Dependencies in Mandarin Chinese.

## My thoughts
-  普通话中的名词不仅携带句法或语义特征，还可能编码量词相关的特征 （量词的特征会encode到noun和adjective）
  - ## 名词、量词和形容词的交互关系
    - ## 量词的双重功能： 量词不仅是一个数量表达工具，还通过语义特征赋值（semantic marking）影响名词的解释和形容词的选择范围。
    - ## 名词的动态语义特征编码： 名词的语义特征并非静态，而是会根据语言上下文（如量词的使用）进行动态调整。例如： “球”在“颗”标记下是具体物体，但在“场”标记下变成抽象事件。这种动态语义特征编码可以解释普通话中的许多量词-名词-形容词组合现象。
    - ## 形容词选择的依赖性：形容词的选择范围不仅取决于名词的语义特征，还受到量词的间接影响。这表明，量词、名词和形容词之间存在复杂的交互关系。
    
- 量词与名词的匹配关系不仅仅是句法上的约束，更可能是认知层面的一种特征编码现象
- 如果 verb-specific cues are derived from the idiosyncratic properties of individual lexical items, such as those readable from the verb read, nouns "plate" and "cup" both have [+shatterable] feature. adjective应该也一样，如果是一颗球，可以红可以绿，但是是一场球，不可以是红色绿色，而是别的形容词，是base在classifier的use上来给noun assign a feature，或者说classifier，改变了这个noun的property。
- 这个是lexicon-specific features
  - 语义搭配的问题，量词可以重新定义名词的特征，从而影响与其搭配的修饰语，汉语中的分类词（如“颗”、“场”）会改变名词的解释，从而影响修饰语的选择范围
  - 实际上重新定义了名词的语义特征：
    -“颗”保留了名词的物理属性（如颜色、形状等）。
    - “场”将名词转化为抽象事件，赋予其与事件相关的特征（如“精彩”）。
  - 语义搭配，指的是词语之间的意义关系是否自然和合理。即使在句法上符合规则，如果语义搭配不合逻辑，句子就会显得怪异或不通顺。
    - 在汉语中，修饰语通常位于被修饰语的左侧，遵循“修饰语 + 被修饰语”的顺序
    - “红色的”是形容词，修饰名词“球”时，语义上表示“这个球的颜色是红色”
    - “精彩的”是一个形容词，用于修饰带有表现力或动态性质的事物（如比赛、表演、电影、演讲等）
- 分类词会根据语境重新分配名词的语义特征，从而影响形容词的搭配。例如：
  - “颗”强调名词的物理特性，因此可以搭配表示颜色、形状等具体特征的形容词。
  - “场”强调名词的抽象特性，因此只能搭配与事件相关的形容词。
  - 在汉语中，分类词（classifiers）起到了类似 Marking 的功能，它们通过赋予名词额外的语义特征来改变其属性。
  
“那一颗红色的球”和“一场精彩的球”可以被视为汉语中的一种 Marking and Morphing 现象，具体体现在：
- 分类词（classifiers）作为 Marking 的工具：
- 分类词为名词分配语义特征（具体 vs. 抽象、物理性 vs. 动态性），从而改变名词的解释。

形容词选择作为 Morphing 的结果：
- 根据名词的语义特征，形容词的选择范围会受到限制（如具体物体选择表示颜色的形容词，抽象事件选择动态性质的形容词）。

## Summary
A significant area of psycholinguistic research has been dedicated to investigating the cognitive mechanisms underlying the processing of long-distance dependencies. This paper ask wehther classifier-specific cues guide the retrieval of their associated nouns. Whether nouns in a classifier language like Mandarin Chinese are encoded with classifier-related features. 
This paper found evidence for a predicted interference effect in retroactive configurations, but no interference in proactive configurations. Found nouns in Mandarin Chinese are indeed encoded with a classifier-specific feature, and lexical-specific cues can not only be derived from verbs, but also from classifiers. Classifier-noun compatibility is gradient rather than categorical. Found asymmetry between target match and target mismatch conditions, where they consistently found facilitatory interference in target mismatch conditions, but no inhibitory interference in target match conditions.

## 主要发现
## 量词可提供词汇特定线索：
- 量词在依赖关系处理中会设置特定的语义检索线索（如“本”与书相关，“张”与平面物体相关）。
- 名词在记忆中可能被编码为具有量词相关特征（classifier-specific features）。
- 量词特征的编码可以通过高维语义表示（high-dimensional semantic representation）来解释：
 ## -  非二元特征：
  -  名词与量词的匹配并非绝对的二元关系（如 [+本] 或 [-本]），而是连续的、渐变的，即量词与名词之间可能存在不同程度的兼容性。
    - 例如，“书”与“本
##  - 高维向量表示：
    - 名词和量词的兼容性可以用高维向量表示，例如将“书”表示为一个包含卷册属性的向量，“本”可以被视为一个与该向量接近的点。名词和量词的匹配程度可以通过向量距离来计算。
##  - 动态记忆模型：
    - 在句法处理过程中，量词会激活特定的线索（如 [+本]），并在记忆中检索与这些线索最相似的名词。
    - 这种机制避免了每次都对整个记忆进行线性搜索，而是通过内容寻址（content-addressable memory）快速定位目标。”的兼容性很高，但“杂志”与“本”可能稍低。

## 回溯干扰（Retroactive interference）显著：
- 当干扰词插入在目标名词和量词之间时，如果干扰词与量词匹配，会出现显著的干扰效应。
- 目标匹配条件：
  - 干扰词匹配时，处理速度变慢（抑制性干扰，inhibitory interference）。
- 目标不匹配条件：
  - 干扰词匹配时，处理速度加快（促进性干扰，facilitatory interference）。

## 前摄干扰（Proactive interference）较弱：
- 当干扰词出现在目标名词之前时，干扰效应不显著。
- 可能原因：
  - 干扰词在记忆中因时间衰减而激活水平降低。
  - 干扰词的句法位置（如嵌套在从句中）可能降低其干扰能力。

## 干扰效应的不对称性：
- 回溯干扰中，促进性干扰（facilitatory interference）比抑制性干扰更容易被观察到。
- 支持了一个“修复机制”（repair-based mechanism）的假设：当依赖关系匹配失败时，检索过程会被触发以修复错误。

## A-Maze 方法的成功应用：
- A-Maze 方法比spr更能检测到干扰效应，尤其是在在线实验中。
- 使用 A-Maze 成功复制了回溯干扰的实验结果。

## Introduction 

## Cue-based retrieval (Lewis and Vasishth (2005))

- 线索-提取理论（cue-retrieval theory）：
- 该理论认为，在语言加工中，我们依赖某些线索（cues）来提取正确的依赖关系。如果出现干扰项，它可能会影响我们选择正确的线索，进而影响语言处理的流畅性。
- Memory retrieval is guided by the cues from the verb that allow the cognitive system to search for the relevant item in memory by direct access, which means a serial search involving every element held in memory is unnecessary.
- cues 可以是
  -  syntactic constraints
  -  morphological or lexical properties of the word
  -  比如 verb complained，需要search for [+subject] [+animate] features


Cue-based retrieval suggests that the parser initiates a search for the relevant linguistic dependent at the retrieval site, such as the verb, based on a set of retrieval cues. 
- 主要predict, distractor match in target match conditions, will cause slowdowns due to cue overload.
- Cue-based retrieval 在 subject-verb agreement dependencies has a limited role
- When a linguistic dependency needs to be completed at a particular word, the parser triggers a search for the linguistic dependent using a content-addressable cue-based mechanism. Interference can arise as a result of the match between the set of cues utilized at retrieval and the number of items in memory that match these cues. 
- Retrieval cues may not function as discrete, binary features but instead operate in a graded, high-dimensional similarity space. 

- Unlike morphosyntactic cues such as number and gender, or subcategorization constraints like animacy, classifiers may rely on cues derived from specific lexical constraints to retrieve a dependent noun that matches the classifier. 

- Whether the distractor must intervene between the co-dependents (e.g., retroactive interference, whereby the distractor noun intervenes between the correct noun dependent and the classifier) or whether the distractor can appear to the left of the dependent elements (e.g., proactive interference, the distractor noun appears before the correct noun dependent and the classifier). 

- Previous work has shown that proactive interference is weaker than retroactive interference, which means the distractor has to intervene between the co-dependents to influence the dependency completion process.
- 如果干扰词在依赖关系形成之前就出现了，这个是非常合理的，Proactive interference（前向干扰）is weaker than Retroactive interference（逆向干扰）

## 干扰类型：

- Retroactive interference（逆向干扰）：干扰项插入到两个依赖元素之间。例如，一个干扰名词（distractor noun）出现在正确的名词依赖项（correct noun dependent）和分类词（classifier）之间。

举例：假设有正确的依赖关系是「名词1 - 分类词」，但「名词2」（干扰词）插入其中，句子的结构变成「名词1 - 名词2 - 分类词」。这种情况下，干扰词直接打断了依赖关系。
- distractor following the target

- Proactive interference（前向干扰）：干扰项出现在依赖元素的左侧。例如，干扰名词（distractor noun）出现在正确名词依赖项（correct noun dependent）和分类词（classifier）之前。

举例：假设正确的依赖关系是「名词1 - 分类词」，但「名词2」（干扰词）出现在「名词1」前面，句子的结构变成「名词2 - 名词1 - 分类词」。这种情况下，干扰词在依赖关系形成之前就出现了。
- distractor linearly precedes the target
- 如果distractor在target word前面，会cause interference，因为during retrieval，the set of retrieval cues will be matched against the features of all items stored in working memory. 

## 核心问题：

- 干扰项的位置是否重要？
- 换句话说，干扰项必须插入到依赖元素之间才能影响语言处理（逆向干扰），还是即使干扰项出现在依赖元素之前，也会对语言处理产生影响（前向干扰）？

## Illusions of grammaticality
- Illusions of grammaticality = facilitatory interference in ungrammatical sentences
- "Illusions of grammaticality" 指的是在某些情况下，人们会错误地认为一个不符合语法规则的句子是符合语法的。这种现象可以通过 facilitatory interference（促进性干扰）来解释。
- 这种错觉通常发生在句子中包含复杂结构或多个元素的情况下。
- 这表明语言处理器有时会受到干扰，导致提取和判断语法的过程出现偏差。

Facilitatory interference（促进性干扰）:
- 这是干扰的一种形式，与一般的抑制性干扰（inhibitory interference）不同。
- 促进性干扰指的是某些干扰项（distractors）实际上有助于语言处理器提取错误的语法线索，从而让人误以为句子语法正确。
- 例子：当句子的某些部分（如干扰词或结构）与正确的语法依赖关系保持一致时，它可能会欺骗语言处理系统，让它判断整个句子为语法正确。
- The key to the cabinets were lost.

## Verb-specific cues and retrieval interference
- verb-specific cues derived from the idiosyncratic properties of individual lexical items, such as those readable from the verb read.
- nouns "plate" and "cup" both have [+shatterable] feature
- found facilitatory interference in target mismatch conditions but no effects in target match conditions.

## Feature percolation
- only morphosyntactic features are involved in feature percolation.
- Feature percolation 是语言学中的一个概念，通常与句法（syntax）和形态学（morphology）相关。它描述了在句法结构中，某些特征（features）如何从一个词或短语传播到更高层级的结构中。特征传播通常遵循特定的规则，主要是语法与形态特征的传播，而这句话强调了只有形态句法特征（morphosyntactic features）参与特征传播。

## 核心概念拆解
- 在句法结构中，某个词或短语的特定特征（如数、性、格、时态等）会传播到更大的句法单位中。
  - 它帮助句法结构中的成分保持一致性（agreement），例如主谓一致（subject-verb agreement）或名词-形容词一致（noun-adjective agreement）。

## Morphosyntactic features（形态句法特征）：

- 这些是与形态学和句法规则相关的特征，主要包括：
  - 数（number）：单数、复数等。
  - 性（gender）：阳性、阴性、中性等。
  - 格（case）：主格、宾格、属格等。
  - 人称（person）：第一人称、第二人称、第三人称。
  - 时态（tense）：过去、现在、将来等。
  - 语态（voice）：主动、被动等。

形态句法特征的传播是句法一致性的重要机制。例如：
- The boy runs. 中，主语“boy”的单数特征传播到谓语动词“runs”，从而保持主谓一致性。

- 在特征传播过程中，只有形态句法特征会被传播，而其他类型的特征（如语义特征或语用特征）不会传播。 换句话说，传播仅限于那些对句法结构有直接影响的特征，而不会涉及像意义、情感等非句法特征。

## Marking and morphing (Bock et al., 2001; Eberhard et al., 2005)
- 句法依赖关系的处理（dependency processing）中，如何通过语义特征（如概念复数和分布性）来影响句法结构的生成和解析。
## - Marking:
  - 这是语言处理中的语义阶段，指的是语言生成或解析时，确定某些语义特征（semantic features），如单复数、分布性、数量等。这些特征在概念层面被激活，并将作为后续句法生成的基础。
## - Morphing:
 - 这是语言处理中的形式阶段，指的是将语义特征（如数、性等）映射到语言的形态形式（morphological forms）上。
- 语义特征对句法的调节作用：
- 句法依赖关系（如主谓一致）不仅是形式上的规则约束，还受到语义特征（如概念复数和分布性）的显著影响。

## Classifier-noun dependencies in Mandarin Chinese
- In Mandarin Chinese, a classifier is typically required when a countable noun is preceded by a numeral or a demonstrative
- In canonical word order, the classifier usually precedes the noun
- Compatibility between a classifier and a noun is usually determined by certain semantic properties of the noun
- Classifiers can be used for nouns outside of their semantic class
  - Gradient effect 

## Method
- SPR
- A-Maze
- Retroactive interference（逆向干扰）：干扰项插入到两个依赖元素之间。例如，一个干扰名词（distractor noun）出现在正确的名词依赖项（correct noun dependent）和分类词（classifier）之间。

- Proactive interference（前向干扰）：干扰项出现在依赖元素的左侧。例如，干扰名词（distractor noun）出现在正确名词依赖项（correct noun dependent）和分类词（classifier）之前。

## Hypothesis 
- longer reading times at the classifier for target mismatch conditions in comparison to target match conditions, as the semantic mismatch between a classifier and its dependent noun has been shown to cause disruptions in processing in various studies

## Participants
- 80 native Mandarin speaker
