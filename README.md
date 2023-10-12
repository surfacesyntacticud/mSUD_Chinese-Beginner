# mSUD_Chinese-Beginner

This treebank is a native mSUD treebank (morpheme level Surface Universal Dependencies) of mandarin chinese.

The sentences of the corpus were taken from the [Chinese Grammar Wiki](https://resources.allsetlearning.com/chinese/grammar/\) (maintaned by AllsetLearning under the Creatives Commons CC BY-NC-SA 3.0 License).

You can browse and query this treebank on the [GREW-Match platform](https://universal.grew.fr/?corpus=mSUD_Chinese-Beginner@latest) as well as its word level equivalent [SUD_Chinese-Beginner](https://universal.grew.fr/?corpus=SUD_Chinese-Beginner@conv)

## Structure of the Treebank
The Treebank is partitioned in 5 parts A1, A2, B1, B2 and C1 that represents different level of difficulty (from easiest to hardest). 

/!\ At the day of October 12th of 2023, 2350 sentences have been hand annotated. But below is the complete distribution of the corpus when it will be finished. 

The corpus is made of around 4300 sentences, with the following distribution : 
- A1 : 382 sentences (3456 tokens , ~ 9.05 tokens per sentences)
- A2 : 1103 sentences (11920 tokens, ~ 10.80 tokens per sentences)
- B1 : 1347 sentences (18236 tokens, ~ 15.54 tokens per sentences)
- B2 : 1441 sentences (24419 tokens, ~ 16.95 tokens per sentences)
- C1 : 300 sentences (5482 tokens, ~ 18.27 tokens per sentences)

 

## Structure of a sentence
Here an example of the meta data that each sentences contains : 
```
# sent_id = 1
# structure = 没 + 有 (+ Obj.)
# text = 我 没有 问题。
# level = A1
# structure_verbose = Negation of "you" with "mei"
# url = https://resources.allsetlearning.com/chinese/grammar/ASGPNV3Q
# text_en = I don't have any questions.
# translit = Wǒ méiyǒu wèntí.
```

PS : At the moment, some of the sentences in the C1 part are missing the pinyin (transliteration)

## Morpheme level of annotation
To be independent of the results of a pre tokenization, we decided to annotate the corpus on the morpheme level. It means that each character is a node/token of the sentence, and relations xxx@m (m for morpheme) are linking characters of a same "word unit".
We will provide in a near future the grew rules for converting to word unit SUD and to word unit UD.

## Conversions
### Prerequesites
You first need to [install grew](https://grew.fr/usage/install/) and pull the [SUD rewriting repository](https://github.com/surfacesyntacticud/tools)
### Convert to SUD (from mSUD)
Given that you cloned the "tools" repo on a sibling level with the current repo 
```
grew transform -grs ../tools/converter/grs/zh_mSUD_to_SUD.grs -config sud -strat zh_mSUD_to_SUD_main -i ./chinese-beginner.A1.mSUD.conllu -o ./chinese-beginner.A1.SUD.conllu
```
### Convert to UD (from mSUD)
```
grew transform -grs ../tools/converter/grs/zh_mSUD_to_UD.grs -config sud -strat zh_mSUD_to_UD_main -i ./chinese-beginner.A1.mSUD.conllu -o ./chinese-beginner.A1.UD.conllu
```

## Contact us
If you have any question or wish to add your contribution, feel free to contact Kirian GUILLER, Qishen WU, Yixuan LI, Yidi HUANG or Yingzi LIU
