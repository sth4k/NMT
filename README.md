# NMT

- [General Training Pipeline](#i-general-training-pipeline)
- [Constrained Machine Translation](#ii-constrained-machine-translation)
- [Useful References](#iii-useful-references)

## chat translation
1. data labeling
2. data preprocess (moses)
  - normalize punctuation
  - remove non-print char
  - tokenize
  - clean based on the length ratio 1.5
  - lowercase
3. apply truecaser or recaser (this should be done before lowercase)
4. learn and apply bpe
  - git clone https://github.com/rsennrich/subword-nmt.git
  - it will put "@@ " to divide words, and can be restored by sed -r 's/(@@ )|(@@ ?$)//g'
  - meaning of bpe_operations and algo?
5. train with fairseq

## I. General Training Pipeline

Raw Text -> Text Cleaning -> Tokenizer -> Apply BPE -> Model Training -> Remove BPE and Detoke -> BLEU

## Tokenizer and detokenizer
--SentencePiece (Google, https://github.com/google/sentencepiece)

direct training from raw sentence, without need for pre-tokenization.
Experiments on SentencePiece
https://github.com/google/sentencepiece/blob/master/doc/experiments.md

## BPE


## Training
### Hyperparameters
    -- hidden neuron size
    -- dropout
    -- learning rate
    -- gradient clip
# Frameworks

## fairseq
https://github.com/facebookresearch/fairseq
torch

## fairseq-py
https://github.com/pytorch/fairseq
pytorch version of fairseq



## II. Constrained Machine Translation

### lexical constraints

E.g. "American peot Edgar Allan Poe", the English phrase "Edgar Allen Poe" must be translated to Chinese word "Ailunpo"


### structural constraints


## III. Useful References

[1] [施杨斌 让商业没有语言障碍 深度学习在阿里机器翻译的应用](https://myslide.cn/slides/9990#)


