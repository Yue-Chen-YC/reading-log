---
tags  : [Model, BERT]
category: [Mandarin, BERT]
---
## Pre-Training with Whole Word Masking for Chinese BERT (Cui et al., 2021)

## Citation 
Cui, Y., Che, W., Liu, T., Qin, B., & Yang, Z. (2021). Pre-training with whole word masking for chinese bert. IEEE/ACM Transactions on Audio, Speech, and Language Processing, 29, 3504-3514.

## My thoughts


## BERT
- Designed to pretrain deep bidirectional representations by jointly conditioning on both left and right context in all Transformer layers
- 2 pre-training tasks
  - Masked Language Model (MLM)
    - randomly masks some of the tokens from the input, and the objective is to predict the original word based only on its context 
  - Next Sentence Prediction (NSP)
    - to predict whether sentence B is the next sentence of sentence A
   
## Chinese BERT
- whole word masking (wwwm)
  - Instead of randomly selecting WordPiece tokens to mask, always mask all of the tokens corresponding to a whole word at once.
  - force the model to recover the whole word in the MLM pre-training task instead of just recover the whole word in the MLM pre-training taks instead of just recovering WordPiece tokens
 
## ERNIE 

- Enhanced Representation through kNowledge IntEgration) is designed to optimize the masking process of BERT, which includes entity-level masking and phrase-level masking.

# MLM as correction (Mac) 
- MLM suffers from the pre-training and fine-tuning discrepancy, where the artificial tokens in the pre-training stage, such as [MASK], never appear in the real downstream fine-tuning task
- MLM as a correction (Mac) as a solution
  - in pre-training taks, we do not adopt any pre-defined tokens for masking purposes, but transform the original MLM as a text correction task, and correct the wrong wrod into the correct one.  

