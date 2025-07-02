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
 


