# FF-Attack
FF-Attack: A backdoor attack framework against Ponzi contract detection models based on fund flow features.

## Overview
FF-Attack is a backdoor attack against Ponzi contract detection models.
It adds hidden triggers to normal smart contracts so they show Ponzi-like fund flows and mislead detection models, while keeping their original functions unchanged.

## Method
Trigger Design: Simulate Ponzi fund flow patterns (tree structures, chain structures, etc.).
Injection Method: Insert triggers into the contract at the Abstract Syntax Tree (AST) level to improve stealthiness.
Attack Execution: Compile the contract to opcode/bytecode and test against detection models.

## Code Structure
```
FF-Attack/
├── ML_learning/                        # Machine learning methods
│   ├── NgramCount/                     # N-gram count features
│   ├── N_TermCount/                    # N-term count features
│   ├── N_TF_IDF/                       # TF-IDF features
│   ├── N_TF-IDF-on-Ngram/              # TF-IDF for N-gram features
│   ├── N_Word2Vec/                     # Word2Vec features
│   ├── code_poisoning_defense/         # KILLBADCODE defense
│   └── SS/                             # Spectral Signature defense
│
└── SCSGuard/                           # Deep learning methods
    ├── data/                           # Datasets
    ├── preprocess_poi.py               # POI preprocessing
    ├── poi_train.py                    # Training 
    ├── poi_eval.py                     # Evaluation 
    └── models/                         # Models
```

### Description
- **ML_learning**: Implements backdoor attacks based on machine learning methods. It includes five feature extraction methods (`NgramCount`, `N_TermCount`, `N_TF_IDF`, `N_TF-IDF-on-Ngram`, `N_Word2Vec`) and two defense mechanisms (`code_poisoning_defense` implements the KILLBADCODE defense, and `SS` implements the Spectral Signature defense, covering all five feature types).

- **SCSGuard**: Implements backdoor attacks based on deep learning methods. It is used for conducting attack experiments against deep learning-based Ponzi contract detection models.

