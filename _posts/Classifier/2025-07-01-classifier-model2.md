---
tags  : [Classifier, Model, BERT]
category: [Mandarin, Classifier, BERT, eye-tracking]
---
## Existence Justifies Reason: A Data Analysis on Chinese Classifiers Based on Eye Tracking and Transformers (Wang et al., 2023)

## Citation 
Wang, Y., Chersoni, E., & Huang, C. R. (2023, December). Existence Justifies Reason: A Data Analysis on Chinese Classifiers Based on Eye Tracking and Transformers. In Proceedings of the 37th Pacific Asia Conference on Language, Information and Computation (pp. 912-921).

## My thoughts
Compare the eye-tracking dataset with BERT prediction for sentences with/without classifiers, found facilitative processing effect for classifiers in human processing, for models, it's beneficial to have classifiers without classifiers for both verbs and nouns. 


Their use of the Wilcoxon rank-sum test for both fixation data and model prediction due to abnormal distribution for the two samples for fixation data (one with a classifier and one without a classifier), shouldn't we log-transform the fixation duration? 
- These fixation durations are indeed (likely) not normally distributed. For analysis, the authors should consider the following. First, (a) do they want to conduct a simple test for differences in means, or (b) do they want to fit a regression model to possibly incorporate other predictors and/or random effects into the model? It seems they went with (a). In that case, because they are analyzing continuous data, they are choosing between a t-test and a Wilcoxon test. T-tests are appropriate only for normally distributed data, but the Wilcoxon test (which is non-parametric) is appropriate for non-normally distributed data as well. If they had gone with (b), which is the current expectation in most top psycholinguistic journals, then they may have considered transforming the fixation times in order to (i) have a continuous, unbounded response variable and/or (ii) ensure normality of the residuals, but that non-normality of a continuous response variable is not in-and-of-itself a problem.
So in short, the test the authors used was appropriate given properties of the data, but these days journals do expect regression models rather than simple tests for a difference in means, like the Wilcoxon test.
I am also surprised that they put so much emphasis on the "reduced by 20.632%", which is the likelihood of type M error in under-powered studies is quite high, so it's likely that this result is an overestimate of the true effect.

## Background
- Recent research suggests that classifiers can facilitate the understanding of subsequent nouns.
- ERP studies found that a mismatch between classifiers and predicted words influences the N400 effect in the human brain, which demonstrated a graded response among the mismatching classifiers with a smaller effect observed for classifiers that were semantically related to the predicted word compared to classifiers that were semantically unrelated (grammar > semantics). 
- verbs vs. classifiers 班 -> 坐： 坐一班飞机，搭一班飞机

## Method 

## Eye-tracking
- Compare the average duration of words with/without classifiers
- 29 nouns that appeared after classifiers more than 5 times, a total of 242 fixations with classifiers, and 1335 fixations on the same word without classifiers.

## Corpus 
- The Database of Eye-Movement Measures on Words in Chinese Reading (Zhang et al., 2022)
- 1718 participants, 8015 Chinese sentences, nearly 1.4 million fixations

## Modeling 
- BERT to predict masked words
- masking noun and classifier
- Word-level BERT (wobert_chinese_base) to predict subsequent nouns and preceding verbs in 2 environments
1. with classifiers
2. without classifiers
- Compare the accuracy, perplexity of the prediction, and semantic similarity between words predicted by BERT when using the MASK token and the target word. 

## Corpus 
Chinese Classifier Dataset
- More than 100 million sentences illustrating the usage of Chinese classifiers


## Research Questions 
1. What is the impact of Chinese classifiers on noun processing in humans?
2. How does the presence or absence of classifiers affect word prediction performance in Chinese sentences?
3. What are the variations in the influence on word prediction among different types of Chinese classifiers?

## Results
- Human processing: Words with classifiers have a significantly shorter average duration (p < 0.05) compared to words without classifiers.
- Wilcoxon rank-sum test = the average duration of a word with classifiers is significantly shorter (P value < 0.05) than the average duration of the same word without classifiers. On average, reduced by 20.632%.
- Different types of nouns, 时间/事情 light nouns, do not have semantic content, which people have to combine aforementioned contexts to understand them, which takes more fixation time.
- 这 / 那 + classifier + noun at the beginning of a sentence requires additional time to determine the referent of this demonstrative structure. 
  - Classifiers are beneficial in language processing in humans, aiding in the comprehension of language.  
- Model prediction: Retaining classifiers significantly facilitates the prediction of the transformer language model for predicting upcoming nouns and preceding verbs.
    - Wilcoxon signed rank test, the semantic similarity is significant
    - The prediction accuracy and average perplexity improve with the presence of the classifier
    - Prediction accuracy for nouns following a classifier is 2.56 times higher than a noun without a classifier (49.89% vs. 19.48%)
    - Average perplexity when using the classifier is significantly lower than without the classifier.
    - Measure words exhibit an unexpected capacity to contribute to this prediction, while event classifiers and approximation classifiers have great advantages in predicting verb semantics compared to general individual classifiers.
- exceptions: 个，种，次
 


