---
tags  : [Screening, Autistic Traits, Individual-difference]
category: [AQ, Screening]
---
## Phonetic imitation from an individual-difference perspective: Subjective attitude, personality and “autistic” traits (Yu et al., 2013)

## Citation 
Yu, A. C., Abrego-Collier, C., & Sonderegger, M. (2013). Phonetic imitation from an individual-difference perspective: Subjective attitude, personality and “autistic” traits. PloS one, 8(9), e74746.

以下是对 Yu, Abrego-Collier & Sonderegger (2013) 的精炼总结，重点放在统计建模与 individual differences（个体差异）分析；最后给出作为“关注个体差异的学者”的评价与启发。

一、研究问题与设计概览
- 目标：考察语音模仿（phonetic imitation，本文聚焦 VOT 的延长）在多层因素影响下的变异性，尤其是个体差异与情境变量如何调制模仿幅度。
- 任务流程（被试内）：产出基线（读 72 个以 /p t k/ 起首的词）→ 听故事（嵌入同一词表，目标词 VOT 被延长 100%）→ 产出测试（同词表）。
- 情境操控（被试间）：故事叙述者的性倾向标签（gay vs. straight）× 故事结局（positive vs. negative）共四条件。
- 个体差异量表：AQ（总分与 5 个分量表，尤其 Attention Switching）、Big Five（OCEAN），工作记忆（RSPAN），以及对叙述者的主观态度（attitude）。

二、统计方法（核心亮点：两步混合效应建模）
作者采用“二步建模”（two-step modeling）来把“基线/产出层面的已知影响”和“个体差异层面的解释变量”分离清楚。

步骤一：控制词级与话语级因素，获得“标准化 VOT 残差”
- 模型：线性混合效应模型（lmer）
  - 因变量：VOT
  - 固定效应：起始辅音（/p/ vs /t/ vs /k/，Helmert 编码）、词频（对数）、音节数（有序多项，含线性与二次项）、两种语速（词内 RATE1、短语内 RATE2）、试次序 TRIAL 及其与 BLOCK（pre/post）的交互
  - 随机效应：被试与词的随机截距；被试对所有主要预测因子的随机斜率（允许相关）
- 处理：剔除 VOT 和语速离群值（±3 SD）、连续变量中心化与标准化、编码细节严格控制
- 目的：在充分控制已知的、强效的 VOT 影响因素（如部位、语速、词长、时序）后，取模型残差作为“标准化的 VOT 值”
- 输出：每个被试×词在 pre/post 两个区段的“标准化 VOT”，据此计算“标准化 VOT shift = post − pre”

步骤二：用个体与情境变量预测“标准化 VOT shift”
- 模型：线性混合效应模型（lmer）
  - 因变量：标准化 VOT shift（每个被试×词一个差值）
  - 固定效应（均为“被试层” predictors）：OUTCOME（positive/negative）、叙述者 SEXUALITY（gay/straight）、被试 GENDER、ATTITUDE（对叙述者态度）、RSPAN、Big Five（O C E A N）、AQ 五分量表（SS, CM, AD, AS, IM）
  - 随机效应：被试与词的随机截距（斜率在尝试后因收敛与贡献小未保留）
  - 变量处理：连续变量中心化并按 2 SD 缩放；类别变量 sum-coding；MCMC 估计 p 值（mcmcsamp 50,000 次）
- 解读：模型截距 = 全体平均的 shift；各固定效应系数 = 该个体/情境变量对 shift 的影响方向与幅度
- 额外报告：R1^2（相对基线随机截距模型的均方预测误差降低率），以及每一预测变量的重要性指标（|β|与删项对 R1^2 的百分比下降）

三、主要结果
总体效应
- 平均而言，没有显著的整体 VOT 延长（模型 2 截距 ~ 0.47 ms, p≈0.29）。即，没有“群体层面”的一致模仿，但个体差异显著。

显著的调制因素（四个稳定因子）
- 态度（ATTITUDE）：越喜欢叙述者（分值越低），越朝其延长 VOT 方向模仿；越不喜欢则出现负向（远离）调整。效应最强（|β|≈4.53 ms/2SD，p<.0001；对 R1^2 贡献最大）。
- 开放性（Openness, O）：高 O 更倾向延长 VOT，低 O 倾向缩短（|β|≈3.53 ms/2SD，p≈.001）。
- AQ 的注意转换（Attention Switching, AS）：AS 分高（注意切换困难、注意更集中）→ 模仿幅度更大（|β|≈2.58 ms/2SD，p≈.014）。
- 故事结局（Outcome）：负面结局条件的模仿（VOT 延长）高于正面结局（差约 2.58 ms，p≈.008）。作者推测与“负性材料的自动警觉（automatic vigilance）→更集中注意”有关。

边缘或不稳定因素
- Conscientiousness 在不同参数/修剪下不稳定（作者谨慎不作为稳定发现）。
- Agreeableness 与 Sexuality（gay vs. straight）在一步式模型里达到显著，但在二步式模型中为边缘或不显著；作者提示两步法可能统计力略低。

无显著影响
- 性别（GENDER）、工作记忆（RSPAN）、AQ 其他分量表多不显著；叙述者的性倾向标签总体不显著（在一步模型中为潜在效应）。

随机效应与解释度
- 被试随机截距方差显著：个体间 shift 差异大（约 −6.8 到 +7.8 ms 的 95% 范围，超出已纳入解释变量的部分）。
- 词项随机截距≈0：词之间的 shift 系统性差异不明显。
- 全部主观/个体变量的整体解释度（R1^2）很小（≈0.00026）：提示虽有显著因子，但总体残差巨大（可解释变异占比很低）。

四、对“个体差异”取向学者的评价与启发
优点
- 严谨的两步混合模型：先消解词项与语速等强力协变量，再用个体与情境层面变量解释“净化后的 shift”，逻辑清楚、可复用。
- 多维个体差异电池：把人格（Big Five）、AQ 分量表、WM（RSPAN）、主观态度并置，能定位哪些个体特质与模仿最相关。
- 统计透明：编码、标准化、离群处理、随机结构、MCMC p 值、变量重要性与 R^2 指标均有交代；并与“一步模型”做鲁棒性对比。
- 理论连接：把“注意/投入（engagement）与选择性注意”引入模仿机制（超越“自动激活”式的 exemplar 模型），并强调情境态度的即时性作用（不依赖长期意识形态）。

局限与改进空间
- 无“未延长 VOT”的对照条件：无法直接验证“shift 是否由暴露引起”。尽管作者用态度等变量的方向性做了合理推断，但未来应加控制组。
- 解释度低（R1^2 极小）：说明还有大量未建模的随机或系统来源（如更细粒度的注意/执行功能指标、社会指示意义的主观解读、语音-知觉敏感度个体差异、动机等）。
- 情境操控的“性倾向标签”并未稳定显著：可能需要更强的社会意义操控、或结合显性/隐性态度测量（IAT）、或操控“说话人可信度/权威/吸引力”多因子。
- 统计功效：两步法基于差值（post−pre）会牺牲一定信息量；作者也承认一步法可能更有力。未来可用 Bayesian 层级一体化模型直接估计 BLOCK×（个体/情境）交互，并对 measurement error 传播更友好。
- 仅看 VOT：建议并行跟踪其他参数（F0、持续时长、韵律、释放噪声谱特征等）和跨特征的协同模仿，以检验“注意权重”假设的维度特异性。

我会如何在后续研究中利用与扩展
- 设计改进
  - 加入控制组（未延长 VOT 的故事），并在同一被试内做条件交叉，明确归因。
  - 同时记录在线注意指标（眼动、瞳孔、二任务干扰、主观投入量表）、生理 arousal（EDA/心率）以检验“负面叙事→自动警觉→注意强化→模仿增强”的通路。
  - 加入执行功能/注意控制更直接的测验（Stroop、Flanker、AX-CPT）、以及听觉精细差别测验（如 VOT 弁别阈值）以区分“检测能力”与“注意分配/监控”的贡献。
  - 操控叙述者的社会意义维度更明确（权威/地位、群际关系、相似性/隶属动机），或用多名 talker 以估计说话人层随机效应。
- 建模强化
  - 采用单步 Bayesian 层级模型，将 BLOCK、词级/句级协变量、被试层个体差异与其交互纳入同一框架，估计不确定性；尝试随机斜率（词对 BLOCK 的斜率；被试对 BLOCK 的斜率做变差解释）。
  - 多维模仿联合建模（VOT 与 F0 等的相关 shift），检验是否存在“维度选择性模仿”与注意权重机制。
- 理论推进
  - 在 exemplar/记忆权重模型中显式引入“注意—参与度—态度”的权重函数，并让社会意义通过“注意权重”调制感知—产出通路。
  - 区分“检测→更新表征→产出”各环节中的个体差异位置（WM/执行功能可能影响的是“监控与选择”，而非资源总量）。

五、一句话结论
这篇论文最有价值的结论是：在没有群体平均模仿的情况下，个体差异与情境评价（喜欢与否、负面情节）强力决定了是否以及如何模仿；开放性与注意切换困难（注意更集中）者更易向目标说话人收敛。这把“注意/投入”机制稳稳地放到语音模仿与音变扩散讨论的中心，也为后续以个体差异为主线的实验与建模提供了清晰路线图。

Summary: Social factors have been suggested as a motivator for imitation, and few studies have established a tight connection between language-external factors and a speaker’s likelihood to imitate. This study investigated the phenomenon of phonetic imitation using a within-subject design in an individual-differences approach. They found that the extent of phonetic imitation by an individual is significantly modulated by the story outcome, the participant’s subjective attitude toward the model talker, the participant’s personality trait of openness, and the autistic-like trait associated with attention switching. They found that the extent of phonetic imitation by an individual is significantly modulated by the story outcome, by the participant's subjective attitude toward the model talker, and the participant's personality trait of openness, and the autistic-like trait associated with attention switching.

Research Questions: 
How does VOT shift as a result of hearing the narrative, across subjects, after controlling for other factors?
Second, what factors affect how much a subject’s VOT shifts?

Overall theoretical contribution: 
Implications for models of speech perception and production, especially exemplar-based models. 
The findings suggest that exposure does not lead to automatic, cumulative convergence at the group level. Instead, imitation is gated by attention and attitude at the individual level. Exemplar updating and subsequent production are modulated by selective attention and engagement, as well as situational evaluations of the model talker. Then this kind of exemplar-based model can account for the phonetic imitation data, and it should consider individual differences, such as the attention-weighting component in the model, which needs to account for attention-related inter-individual variation. 

Method: 
Production study with three blocks 
Baseline production block where subjects produced a list of 72 /p t k/-inital words in the carrier sentence, “say __ again”.
Exposure block: first-person narrative in which the same words were embedded, and VOTs of the target words in the story were extended by 100% using Praat.
Narrative consisted of a male recounting the experience of a recent blind date. 
Post-exposure test block, the subjects produce the same word list again in a different randomized order.
2 x 2 design 
2 factors: 
Perceived sexual orientation of the narrator (homosexual vs. heterosexual)
The gender of the date was varied for each storyline 
Homosexual version = VOTs of the target words were extended
Heterosexual version = replacing the proper names and pronouns in the extended-VOT recording with the gender-appropriate names of pronouns 
Outcome of the story (positive = hit it off with the date and was happy about it vs. negative = went home alone)

Individual Difference Measures: 
Subject’s age
Second language knowledge
Assessment of own sexual orientation (from 1 = exclusively heterosexual to 7 = exclusively homosexual)
Feelings towards the talker (from 1 = very positive to 7 = very negative)
Likelihood of behaving in the same way in a similar situation (yes/no)
Autism-Spectrum Condition (ASQ): Likert scale (1 - 4)
a total AQ score was calculated by summing all the scores for each of the items, with a maximum score for 200 and a minimum score of 50, subscales have a maximum score of 40 and minimum score of 10, high scores = traits associated with ASC: lower social skills, difficulty in attention switching, higher attention to detail and patterns, lower ability to communicate and lower imagination 
Short, self-administered scale for identifying the degree to which any individual adult of normal IQ may have traits associated with ASC. AQ is not a diagnostic measure, but it has been clinically tested as a screening tool
50 items, 10 questions assessing 5 subscales: social skills, communication, attention to detail, attention-switching, and imagination 
Working memory capacity (Automated Reading Span Task, RSPAN)
Participants were presented with a series of sentences on a computer and were asked to indicate whether the sentence made sense by clicking true or false on the screen. Then, a letter was presented for participants to hold in memory, for a total of 75 letters in 15 sets. 
Scores calculated with the partial-credit unit scoring method
Personality (Big Five)
5 board personability dimensions: openness, conscientiousness, extraversion, agreeableness, neuroticism 
Each dimension is computed as the mean score for questions associated with the dimension. 
High AQ individuals are associated with high Neuroticism, low Extraversion, and low Agreeableness or low Conscientiousness 

Production Measures: 
Target word VOTs 
VOT shift (before and after exposure, change of VOT)

Statistics: 
Two-step modeling 
Model 1 (linear mixed effect): Model the effects of properties of all factors on VOT, except whether the subject has heard the narrative yet or not. Residuals = VOT values normalized for speaking rate, properties of the host word, and idiosyncratic by-subject and by-word differences 
How VOT depends on word-level and utterance-level predictors: 
Frequency, initial consonant, length in syllables, and two measures of speaking rate, and the within-block position of the utterance
Model formula: VOT~CONSONANT+FREQUENCY+SYLLABLES+RATE1+RATE2+ TRIAL+TRIAL : BLOCK+(1+ CONSONANT+FREQUENCY+SYLLABLES+ RATE1+ RATE2+ TRIAL+TRIAL : BLOCK D SUBJECT)+(1D WORD).
Model 2 (linear mixed effect): Effects of subject-level variables (e.g., RSPAN, attitude towards the narrator, narrative outcome, subject’s gender, Big 5 personality, and AQ subscores) on the amount of shift. 
Address two questions: 
The value of its intercept corresponds to how much overall VOT shift occurs
The values of its coefficients describe how different subject-level variables affect the amount of shift.
Model formula: SHIFT ~ GENDER + ATTITUDE + SEXUALITY + OUTCOME + RSPAN + O + C + E + N + A + AS + SS + CM + IM + AD + (1D SUBJECT) + (1D WORD).

One-step modeling (earlier version of this study)
Yields similar results to Model 2: significant effects of outcome, Openness, attitude, and amount of shift, all in the same directions in Model 2
There are two additional subject-level predictors which is also significant: agreeableness and the narrator's sexual orientation 
It might be that the two-step model has less statistical power than the one-step model to detect factors affecting the amount of VOT shift 

Results: 
Overall: They found phonetic imitation to be highly variable, both in terms of contexts and across individuals. They also found certain aspects of the social and cognitive makeup of the subject strongly influence the extent of phonetic imitation, such as significance on ASQ and Big Five, which shows that individuals whose personality reflects greater sense of openness, strong attention focus tend to approximate the narrator’s VOT more than those with the opposite personality and autistic-like traits, but no significance for working memory as measured by RSPAN for individual difference analysis. The results suggested that success in phonetic imitation might not be directly related to the availability of attentional resources per se, but rather to the monitoring and allocation of attentional resources, both of which are within the purview of the executive-function process. 
Model 1: consonant, initial consonant, number of syllables, syllables (word), syllables (phrase) are significant predictors
By-word and by-subject random intercepts are also significant (e.g., using the likelihood ratio test)
Model 2: 5 predictors have significant effects on the amount of normalized VOT shift, which means the individual subjects did shift towards or away from the narrator, as a function of some subject-level predictors: Conscientiousness = not consistently significant under different model parameterizations = rule out, Attitude, Outcome, Openness, Attention-switching 



## My thoughts
- They found significance on ASQ and Big Five, but no significance for working memory as measured by RSPAN
- If working memory capacity is shown to have an effect on ignoring irrelevant or interfering information and maintaining focus on a specific goal, this seems to be an important factor for individual difference factors, but this paper did not find significance in this
  - I should look for tasks on working memory capacity.
  - Working memory capacity also affects sentence processing! (MacDonald MC, Christiansen MH (2002) Reassessing working memory: Comment on Just and Carpenter (1992) and Waters and Caplan (1996). Psychological Review 109: 35–54.)
  - Autistic traits can be measured by the ASQ or the empathy quotient
    - shown to significantly correlate with individual personality traits and social network characteristics
    
## Summary 
Overall, this paper offers further evidence that the extent of phonetic imitation is higher regulated by individual-level variables, such as an individual's judgement of their interlocutor and the social and cognitive profile of the individual. Phonetic imitation: a process by which the production patterns of an individual become more similar on some phonetic or acoustic dimension to those of their interlocutor. This study looks at the phenomenon of phonetic imitation using a within-subject design embedded in an individual-differences framework (e.g., autism-spectrum, working memory, personality). Subjective perspectives on phonetic imitation, the participants assigned to one of the four experimental conditions: sexual orientation of the narrator, or outcome of the story. They found that the extent of phonetic imitation by an individual is significantly modulated by the story outcome, by the participant's subjeciyive attitude toward the model talker, and the participant's personality trait of openness and the autistic-like trait associated with attention switching. 

## Research Questions 
1. How does VOT shift as a result of hearing the narrative across subjects after controlling for other factors
2. What factors affect how much a subject's VOT shifts?

##  Key Concepts
- **phonetic imitation = convergence**
- **phonetic divergence = reverse process**
- **Communication Accommodation Theory**: speech convergence phenomena as motivated by an individual's desire for social acceptance and identification with a particular social group.

## Individual differences dimensions 
**1. working memory capacity (WMC)**: the ability to control attention and deal with irrelevant information, and not simply the amount of information that can reside in working memeory. = individual differences are not due to some limited amount of activation available to the working memory system but to an indicidual's ability to ignore irrelevant information (on the basis of a specific relevant goal) through the control of attention
  - individuls with lower WMC are less able to utilize executive control to ignore irrelevant or interfering information and maintain focus on a specific goal. whereas the opposite is true for high-WMC individulas.
  - working memory has an effect in speech processing, increase WM load has been shown to slow down spoken word recognition, high working memory individuals shown less perceptiual compensation for coaritculation and less biased toward hearing legal sound sequences than low working memeory individuals. 
2. cognitive processing style
- personality traits
- psychological dimensions representing preferences and consistencies in an indivudal's particulat manner of cognitive functioning (acquiring or processing information)
- recent studies found that across-indivudal variation in perceptual and production norms is determined in part by individual variability in cognitive processing style
  - traits associatd with the Autism-Spectrum Condition, reulst in deficits in social interaction, communicaiton, behavioral flexibility and affects 1% of the popultaion.
  - ASQ measures Autistic-like traits within the neruotypical population, which are individuals without clinically autisitc
  - negatively correlated with the extent of identification shift associated with the Ganong effect which is the bias in categorization in the direction of a known word.
  - Ganong effect（加农效应）是指在语音感知中，语音-语义互动导致的“词汇偏向”现象：当一个音位在语音上模糊不清、可被解释为两个音素之间（例如 /d/ 与 /t/ 的边界音）时，听者更倾向于把它知觉为能组成真实词的那个音素，从而将整个刺激听成一个现有词。
  - significant associations between autistic-like traits and perceptual compensation for contextual variation in speech (vocalic context, talker voice, phonotactic contexts)
  - higher ASQ = stronger perceptual compensation for coarticulation than those with lower ASQ
  - lower ASQ = stronger phonetactic effects on speech perception than higher ASQ
  - Individuals with ASC have been shown to exhibit enhanced perceptual processing of fine-grained auditory information
  - more autistic-like trait-related cognitive processing styles might be particularly sensitive to fine phonetic differences
  - cogntive theorties of autism hold that individuals with autism have difficulties intergrtating perceptual information with higher order language processing (weak central coherence), neurotypical individuals with higher AQ, even if they might be better at detecting fine phonetic details, they also might have difficulties utilizing the perceived fine phonetic differences in their own speech production to affect discernible phonetic imitation. 

## Background
- speakers will not imitate if the novel phonetic feature endangers phonetic contrasts (unaspirated vs. aspirated)
- socio-biological factors also play a role: Men imitate more than women in the map task, but less than women in the shadowing task. Language distances: greater imitation is found in same-dialect conversational pairs than in either different-dialect pairs or different L1 pairs. 

## Method
- Procedure
  - Production task with 3 blocks
    - baseline production block: produce 72 /p t k/ initial target words in random order in the sentence "say _ again"
    - words selected from CELEX2, evenly distributed by token frequency quartile and by initial consonant
    - exposure block: subjects heard a constructed first-person narrative in which the words were embedded, and the VOT of the target words in the story was extended by 100%
    - <img width="553" height="701" alt="Screenshot 2025-08-25 at 12 27 21" src="https://github.com/user-attachments/assets/eea81804-a4dd-4870-83fc-8892e22f0c66" />
    - post-exposure test block, the participants need to produce the same word list again in a different randomized order
    - include questions about the subject's age, second language knwoledge assessment of own sexual orientation
      - 1 = exclusively heterosexual to 7 = exclusively homosexual
    - feelings towards the talker
      - 1 = very positive to 7 = very negative
    - likelihood of behaving in the same way in a similar situation (yes or no)
    - whether anything unusual was noticed in the talker's speech 
  - neurocognitive and personality measures
    - ASQ
      - 50 items (10 questions assessing 5 subscales: social skills, communication, attention to detail, attention-switching, imagination)
      - Likert scale 1-4 (original ASQ)
      - a total ASQ score was calculated by summing all the scores for each of the items
      - maximum score of 200, minimum score of 50
      - subscales: maximum score of 40, minimum score of 10
      - higher scores = traits associated with Autism
        - lower social skills, difficulty in attention switching/stronger focus of attention, higher attention to detail and patterns, lower ability to communicate, lower imagination
    - Big Five Inventory: five broad personality dimensions
      - Openness, Conscientiousness, Extraversion, Agreeableness, Neuroticism
      - calculated as questions associated with the dimension
      - High AQ individuals are associated with high Neuroticism, low Extraversion, low Agreeableness, or low Conscientiousness
    - Automated Reading Span Task (RSPAN)
      - working memory capacity
      - sentences on computer (the ranger told the hiker to look out for snakes)
      - ask to indicate whether the sentence makes sense or not (True or False)
      - Then a letter was presented for participants to hold in memory
        - 75 letters in 15 sets
      - score calculated with the partial-credit unit scoring method
      - order is randomized 

## Participants 
- 93 subjects, 2 subjects were lost, 1 subject failed to follow the procedure, 6 participants did not finish the RSPAN or one of the questionnaires (AQ or Big Five)
- remaining 70 words by 84 subjects
- AQ score range 102 - 110.5, SD = 71-150 or 78-155

## Analyses
- Mixed-effect regression models are robust to unbalanced designs
- 2 Models
  **1. The effects of properties of all factors on VOT**, except whether the subject has heard the narrative yet or not
     - residuals of the model are VOT values that are normalized for speaking rate, properties of the host word, idiosyncratic by-subject and by-word differences
     - calculate the normalized VOT shift: the difference between the subject's pre-narrative and post-narrative normalized VOT values for the word
     - properties of the host word (word-level predictors)
     - individual utterance (utterance-level predictors)
     - narrative condition (outcome, sexuality)
     - subject (all other predictors)
    - fixed-effect terms: frequency, consonant, syllables, rate 1, and rate 2
    - by-subject random slopes for all five variables to allow for by-subject variability in the effect of each variable on VOT
    - VOT, CONSONANT+FREQUENCY+SYLLABLES+RATE1+RATE2+ TRIAL+TRIAL : BLOCK+(1+ CONSONANT+FREQUENCY+SYLLA-BLES+RATE1+ RATE2+ TRIAL+TRIAL : BLOCK D SUBJECT)+(1D WORD)
  **2. The effects of subject-level variables (RSPAN, attitude towards the narrator) on the amount of shift**
     - the value of its intercept = how much overall VOT shift occurs
     - Values of its coefficients describe how different subject-level variables affect the amount of the shift
     - Amount of the normalized VOT shift depends on subject-level predictors: the narrative outcome, the narrative's sexual orientation, the subject's gender, attitude towards the narrator, RSPAN, Big Five, ASQ
     - continuous predictors are centered
     - gender, sexuality, and outcome were sum-coded (contrast-coded)
     - SHIFT, GENDER + ATTITUDE + SEXUALITY + OUTCOME + RSPAN + O+ C + E + N + A + AS + SS + CM + IM + AD + (1D SUBJECT) + (1D WORD)
<img width="889" height="601" alt="Screenshot 2025-08-25 at 12 53 53" src="https://github.com/user-attachments/assets/65916630-c6b0-4ffd-9f76-dc33598e54d5" />

## Results
- **Model 1**
<img width="555" height="522" alt="Screenshot 2025-08-25 at 13 07 51" src="https://github.com/user-attachments/assets/b01291dc-eb24-4a20-b020-841ba0655b86" />
<img width="872" height="563" alt="Screenshot 2025-08-25 at 13 09 11" src="https://github.com/user-attachments/assets/3dae3bc8-025f-4de4-b04d-acd60be2b635" />
- **Model 2**
<img width="558" height="673" alt="Screenshot 2025-08-25 at 13 13 31" src="https://github.com/user-attachments/assets/ff03f916-47ec-4fed-83f4-b3d3c81bfdee" />
<img width="856" height="715" alt="Screenshot 2025-08-25 at 13 13 56" src="https://github.com/user-attachments/assets/8e0ad001-ebd0-44d8-8eaf-b4576fd7b42c" />
<img width="552" height="628" alt="Screenshot 2025-08-25 at 13 15 22" src="https://github.com/user-attachments/assets/2772cc15-36ed-40bb-be8a-23db2d291a32" />

## Discussion
- Subjects with a positive attitude towards the narrator increase VOT more than subjects with a negative attitude towards the narrator
- dynamics of VOT imitation were modulated by speaker attitude and narrative outcome, but not speaker gender or perceived sexual orientation of the narrator
- Certain social and cognitive makeup of the subject strongly influences the extent of phonetic imitation
  - A greater sense of openness and strong attention focus tend to approximate the narrator's VOT more than those with the opposite personality and autistic-like traits
  - openness indexes an individual's level of engagement with perceptual, sensory, and abstract and semantic information
    - The level of engagement with the exposure materials matters
  - more focused and are not accustomed to constant attention switching = high attention switching subcore of ASQ, more attuned to the fine-grained phonetic fluctuations in the exposure materials = increasing the chance of such phonetic attributes being imitated 
