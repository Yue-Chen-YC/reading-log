---
tags  : [Classifier, Model, BERT]
category: [Mandarin, Classifier, BERT]
---
## HUsing BERT for choosing classifiers in Mandarin (Järnfors et al., 2021)

## Citation 
Järnfors, J., Chen, G., van Deemter, K., & Sybesma, R. (2021, August). Using BERT for choosing classifiers in Mandarin. In Proceedings of the 14th international conference on natural language generation (pp. 172-176).

## My thoughts

Future Direction
- Comparsion with Human judgment 
- Asking the model to output the most probable classifier from all possible classifiers only


## 2 Models on BERT

1. Unsupervised way (predicting classifiers by unmasking masked tokens)
    - Replace the classifier indicator <CL> with the [MASK] symbol of BERT and ask BERT to unmask it
2. Supervised way (fine-tuning BERT on the task of classifier prediction)
    - Fine-tune BERT on the CCD corpus as a multi-class classification task, where there are 172 classifier classes. 


## Research Questions 
1. Since BERT models context closely and is pertained on large scale corpora, they expect it to outperform other models
    - True
2. How do the two BERT-based models compare? Although they expect fine-tuned BERT to outperform unsupervised BERT.
3. How well BERT can handle classifiers that add information (e.g., measure words, plurality and politeness)


## 4 models and 1 corpus 

Models
1. Unsupervised way (predicting classifiers by unmasking masked tokens) BERT
2. Supervised way (fine-tuning BERT on the task of classifier prediction)
3. LSTM-based system
  - a system or model that utilizes Long Short-Term Memory (LSTM) networks, a type of recurrent neural network (RNN), to process and analyze sequential data
5. Rule-based model
   - Given a head noun, assign the most frequent classifier associated with it in the training data

Corpus
CCD corpus (ChineseClassifierDataset)

## Results
 
Fine-tuned BERT performed the best, and the LSTM model performed the second best, the unsupervised BERT model followed next, and the rule-based model came last. 
Fine-tuned BERT struggles to predict classifiers that add information (measurement, plurality, politeness)

Classifier categories 
- True classifier, highest frequency, highest accuracy 
- Measure words, second frequency, third accuracy 
- Dual classifier, third frequency, second accuracy 

Distance between the classifier and the head noun 
- For correct predictions, the average distance is 1.04, for incorrect predictions, it is 1.15
- Unpaired t-test confirms the distance has a negative effect on the model’s performance (p < 0.001)


