---
tags  : [Proficiency, Self-report]
category: [Bilingualism, Picture Naming, Language Test]
---
👉 See full BibTeX file: [library.bib](../library.bib)

## Predicting proficiency (Neveu et al., 2025)

## Citation 

- Neveu, A., Garcia, D. L., Escobedo, B., Vazquez, P. E., Mejia, M., Hoversten, L. J., & Gollan, T. H. (2025). Predicting proficiency. Bilingualism: Language and Cognition, 1-18.

## Summary 

This paper looked at different objective tests (e.g., MINT Sprint, lexical-decision, category fluency, etc) for language dominance, balance, English and Spanish proficiency, tested on Oral Proficiency Interview (OPI), and which one tends to be the strongest predictor. They tested 80 Spanish-English bilinguals and found that MINT Sprint tends to be the strongest predictor, and lexical decision and category fluency (which is time-consuming to score) come next. They found that bilinguals who said their spoken proficiency is balanced tended to be more balanced on objective measures than bilinguals who said they were English-dominant, and bilinguals who self-rated as balanced tended to be objectively less balanced than bilinguals who self-reported they are Spanish-dominant. There is an overall superiority of objective than self-report measures, which replicates previous studies of Gollan et al., 2023 on MINT-Sprint studies. No self-report measure outperformed the MINT-Sprint as a single predictor for any of the four measures of interest (dominance, balance, Spanish, and English). MINT-Sprint was strong for predicting language dominance, and LDT added predictive power for balanced and Spanish scores; category fluency contributed to the prediction of English scores. This could be due to the differences between tasks, such as for production tasks (e.g., picture naming) it requires the speaker to go from concepts to words, and for letter fluency task it requires speakers to search lexicon in real words and non-words but not production, which is more vulnerable to language switches and testing order effects, which would be measures for cognitive processing but not to language proficiency. 

##  Key Concepts
- **Proficiency**: how quickly, accurately, and easily a person can retrieve words and other linguistic structures and the facility of language use across various communicative contexts (Hulstijn, 2011), and spans four modalities: speaking, understanding, reading and writing.
- **Dominance**: Which language is more proficient? Key variables that influence dominance are AOA, frequency, context of use, formal education, and language immersion. 
- **Balance**: relative proficiency in two languages. 

## Research Aim
There is no standardized method for measuring language proficiency on bilingualism; researchers do not agree on how proficiency should be measured, different bilinguals tend to interpret self-rating scales differently, and self-ratings of proficiency (e.g., LEAP-Q) tend to be subjective and vulnerable. This study is designed to determine which objective measures 

## Method
- **Participants** = 80 Spanish-English bilinguals, English-dominant = 52, Spanish-dominant = 24, Balanced = 4
- **OPI (interview questions and picture description)**
- **MINT Sprint 2.0** (https://osf.io/7r9mq/)
- **Category fluency task** 
- **Letter fluency task**
- **Lexical decision task** (extended version of LexTALE, 100 words and 50 nonwords) - similar to Duolingo Language test
    - Improve matching across English and Spanish, because the words in English have lower frequency and are longer on average than Spanish words  (to match length and frequency)
    - Used Wuggy (multilingual pseudoword generator, https://github.com/WuggyCode/wugg)

## Analyses
- To find out which measure most accurately predicts 
    - Language dominance 
    - Proficiency in two languages is balanced 
        - Dominance score: subtracting Spanish score from English score (e.g., English score of 9, Spanish score of 7, dominance score = 9 - 7 = 2)
        - Balance score: dividing the lower score by the higher score on the same measure completed in both languages (e.g., 7 / 9 = 78% bilingual)
    - Proficiency in Spanish 
    - Proficiency in English
- Divided bilinguals into 3 groups 
    - Give two 7 (maximum possible rating) for both languages 
    - One 7 in one language 
    - Did not give any 7 in two languages

## Results
- There is a difference between which measure most accurately predicts in two languages 
    - Spanish: Best predictor for dominance is MINT Sprint, then category fluency > letter fluency 
    - English: MINT Spring first pass score > category fluency > letter fluency > H-LDT
- Self-reports were not strongly correlated with OPI scores
    - **Predicting language dominance** (build linear regression models with different structures)
        - **Objective measures only**: 
            - MINT and LDT balance score 
                - Higher MINT = higher OPI balance 
                - Higher LDT = higher OPI
        - **Subject measures only**: 
            - Balance score for average self-rated proficiency and proportion of life immersed 
                - Higher Balance score for average self-rated proficiency = higher OPI
                - More immersion = less balance in OPI scores
        - **Object and subject measures**: 
            - retained all predictors
                - Higher MINT = higher OPI 
    -  **Predicting Spanish proficiency**
        - **Objective measures only**: 
            - Spanish LDT, MINT and category fluency task 
                - Higher LDT = higher OPI Spanish scores 
                - Higher MINT = higher OPI
                - Higher Spanish category fluency = higher OPI 
        - **Subject measures only**: 
            - proportion of life immersed, average self-rated Spanish proficiency, age of regular use of Spanish and percent of Spanish use growing up
                - Higher proportion of life immersed = higher OPI
                - Higher average self-rated Spanish proficiency = higher OPI
                - Earlier regular use of Spanish = higher OPI
                - Higher percentage of use of Spanish did no significantly predict higher OPI
        - **Object and subject measures**: 
            - Only objective and self-report predictors that are significant in previous models 
                - Higher MINT = higher OPI 
                - Higher Spanish H-LDT = higher OPI 
                - Higher Spanish category fluency = higher OPI
                - Earlier regular use of Spanish = higher OPI
                - Main effect of average self-rate proficiency is not significant 
                - Main effect of proportion of life immersed in Spanish is also not significant 
    -  **Predicting English proficiency**
        - **Objective measures only**: 
            - MINT English first pass, category fluency at 45s in English
                - Higher category fluenc = higher OPI 
                - Slower MINT first pass efficiency scores = lower OPI
        - **Subject measures only**: 
            - Age of regular use of English
                - later the age = lower OPI
        - **Object and subject measures**: 
            - Only objective and self-report predictors that are significant in previous models 
                - Higher MINT first pass efficiency scores = lower OPI 
                - Higher English category fluency = higher OPI
                - Age of regular use of English is not significant

