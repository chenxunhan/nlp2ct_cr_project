# TASK DESCRIPTION
<!-- 使用Prompt，来源[Is ChatGPT A Good Translator? A Preliminary Study](https://arxiv.org/abs/2301.08745)对数据集 zh.source 和 test.true.en，来源[YutongWang1216/CR-NMT/data/cr_testset](https://github.com/YutongWang1216/CR-NMT/tree/main/data/cr_testset)进行翻译，并对翻译结果进行评分，评分指标借鉴[Revisiting Commonsense Reasoning in Machine Translation: Training, Evaluation and Challenge](https://aclanthology.org/2023.acl-long.866/)等 -->
<!-- 使用proprot 来做1200条数据集，然后做论文里的评分，最后对照 -->
<!-- 测试指标
用50条数据，一次翻译一个，看下是不是跟现在的结果一样，句子的前半部分一样 -->
sentence-level evalation

# PROMPTS  
  
TP1 
Translate these sentences from [SRC] to [TGT]: 

TP2 
Answer with no quotes. What do these sentences mean in [TGT]? 

TP3 f
Please provide the [TGT] translation for these sentences:

[SRC]=Chinese [TGT]=English

# PAPER REFERENCES
[The Box is in the Pen: Evaluating Commonsense Reasoning in Neural Machine Translation](https://aclanthology.org/2020.findings-emnlp.327.pdf)
[YutongWang1216/CR-NMT/data/cr_testset](https://github.com/YutongWang1216/CR-NMT/tree/main/data/cr_testset)
[Retrieval Augmentation for Commonsense Reasoning: A Unified Approach](https://arxiv.org/pdf/2210.12887.pdf)
[Is ChatGPT A Good Translator? A Preliminary Study](https://arxiv.org/abs/2301.08745)
[How Good Are GPT Models at Machine Translation? A Comprehensive Evaluation](https://arxiv.org/abs/2302.09210)

# TBA
[Retrieval Augmentation for Commonsense Reasoning: A Unified Approach](https://arxiv.org/pdf/2210.12887.pdf)这篇不着急看，如果评测还有很大的提升空间，可以再看看retrieval-based的方法

# CHATGPT API

# EVALUATION
## For 50 sentences each time
This is evaluation of ChatGPT-3.5 translation, where prompt is passing 50 sentences each time.

Testing TP1 translation(BLEU):
TP1 BLEU: 0.29861622524500175

Testing TP1 translation(BERT SCORE):
TP1 avg_bert_score[P, R, F1]: [0.9404323101043701, 0.9407292604446411, 0.9405114650726318]

Testing TP1 translation(Bleurt Score):
TP1 avg_bleurt_score: 0.3482626240638395

Testing TP2 translation(BLEU):
TP2 BLEU: 0.2960195988951252

Testing TP2 translation(BERT SCORE):
TP2 avg_bert_score[P, R, F1]: [0.9402866363525391, 0.9401487112045288, 0.9401476979255676]

Testing TP2 translation(Bleurt Score):
TP2 avg_bleurt_score: 0.34887727711970606

Testing TP3 translation(BLEU):
TP3 BLEU: 0.28895951120580804

Testing TP3 translation(BERT SCORE):
TP3 avg_bert_score[P, R, F1]: [0.9387385845184326, 0.9389855861663818, 0.9387936592102051]

Testing TP3 translation(Bleurt Score):
TP3 avg_bleurt_score: 0.30952103921522695
## for 1 sentence each time
Testing TP1 translation(BLEU):
TP1 BLEU: 0.3089671865725252

Testing TP1 translation(BERT SCORE):
TP1 avg_bert_score[P, R, F1]: [0.9439606666564941, 0.9445890188217163, 0.9442088007926941]

Testing TP1 translation(Bleurt Score):
TP1 avg_bleurt_score: 0.36860787082463503

Testing TP2 translation(BLEU):
TP2 BLEU: 0.3003483421904474

Testing TP2 translation(BERT SCORE):
TP2 avg_bert_score[P, R, F1]: [0.9433439373970032, 0.9430471062660217, 0.9431304931640625]

Testing TP2 translation(Bleurt Score):
TP2 avg_bleurt_score: 0.3619335639104247

Testing TP3 translation(BLEU):
TP3 BLEU: 0.3106092340997083

Testing TP3 translation(BERT SCORE):
TP3 avg_bert_score[P, R, F1]: [0.9442692995071411, 0.9449902176856995, 0.9445641040802002]

Testing TP3 translation(Bleurt Score):
TP3 avg_bleurt_score: 0.3694909633261462

# OBSERVATION
## for 1 sentence each time
tp1-55:(Note: The translation is literal, as the sentence did not provide any contextual information)
tp1-331:show Chs + Eng
tp2-14,18:The sentence means "..."
The meaning of this sentence in English is "