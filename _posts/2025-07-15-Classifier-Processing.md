---
tags  : [Classifier, Processing]
category: [Mandarin, Classifier, Cue-based retrieval]
---
## Similarity-Based Interference in the Processing of Classifier-Noun Dependencies in Mandarin Chinese (Hao et al., 2024)

## Citation 
Hao, H., Fuchs, Z., & Vasishth, S. (2024). Similarity-Based Interference in the Processing of Classifier-Noun Dependencies in Mandarin Chinese.

## My thoughts
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

## Summary
A significant area of psycholinguistic research has been dedicated to investigating the cognitive mechanisms underlying the processing of long-distance dependencies.

This paper found evidence for a predicted interference effect in retroactive configurations, but no interference in proactive configurations. 


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

## Method

