# Folder + File Description
- bleurt and CR-NMT-main folders are used for bleurt and CR accuracy of Entity-Aware BERTSCORE evaluation
- dataset folder includes both chinese source text used for translation, and right english translation text of chinese source translated folder includes all translation engines' translation of chinese source text
- code.ipynb is self-descriptive, just read about it


# TASK DESCRIPTION
<!-- 使用Prompt，来源[Is ChatGPT A Good Translator? A Preliminary Study](https://arxiv.org/abs/2301.08745)
对数据集 zh.source 和 test.true.en，来源[YutongWang1216/CR-NMT/data/cr_testset](https://github.com/YutongWang1216/CR-NMT/tree/main/data/cr_testset)进行翻译，
并对翻译结果进行评分，评分指标借鉴[Revisiting Commonsense Reasoning in Machine Translation: Training, Evaluation and Challenge](https://aclanthology.org/2023.acl-long.866/)等 -->
<!-- 使用proprot 来做1200条数据集，然后做论文里的评分，最后对照 -->
<!-- 测试指标
用50条数据，一次翻译一个，看下是不是跟现在的结果一样，句子的前半部分一样 -->
<!-- sentence-level evalation
1. 重新计算一下CR accuracy of Entity-Aware BERTSCORE
    加上CL_SA、CT_SA、LA三个子集的结果
    https://github.com/YutongWang1216/CR-NMT 中包含CR accuracy of Entity-Aware BERTSCORE的计算方法
2. 使用NLLB、Google API、DeepLAPI 翻译测试集test.true.en，并计算分数 -->

# PROMPTS  
  
TP1 
Translate these sentences from [SRC] to [TGT]: 

TP2 
Answer with no quotes. What do these sentences mean in [TGT]? 

TP3 f
Please provide the [TGT] translation for these sentences:

[SRC]=Chinese [TGT]=English

# PAPER REFERENCES
- [The Box is in the Pen: Evaluating Commonsense Reasoning in Neural Machine Translation](https://aclanthology.org/2020.findings-emnlp.327.pdf)
- [YutongWang1216/CR-NMT/data/cr_testset](https://github.com/YutongWang1216/CR-NMT/tree/main/data/cr_testset)
- [Retrieval Augmentation for Commonsense Reasoning: A Unified Approach](https://arxiv.org/pdf/2210.12887.pdf)
- [Is ChatGPT A Good Translator? A Preliminary Study](https://arxiv.org/abs/2301.08745)
- [How Good Are GPT Models at Machine Translation? A Comprehensive Evaluation](https://arxiv.org/abs/2302.09210)

# TBA
[Retrieval Augmentation for Commonsense Reasoning: A Unified Approach](https://arxiv.org/pdf/2210.12887.pdf)这篇不着急看，如果评测还有很大的提升空间，可以再看看retrieval-based的方法

# EVALUATION
## METIC LIST
- [The Box is in the Pen: Evaluating Commonsense Reasoning in Neural Machine Translation](https://aclanthology.org/2020.findings-emnlp.327.pdf)
    - Reasoning consistency
    - Commonsense Reasoning accuracy
- [YutongWang1216/CR-NMT/data/cr_testset](https://github.com/YutongWang1216/CR-NMT/tree/main/data/cr_testset)
    - Entity-Aware BERTScore
    - Commonsense Reasoning Accuracy
    - Meta-Evaluation of Commonsense Reasoning Metrics
        - Prob
        - BLEU
        - BLEURT
        - 卡方检验 (Chi-Square Test)
        - 肯德尔等级相关系数 (Kendall Rank Correlation Coefficient)
        - 方差分析 (Analysis of Variance, ANOVA)
- [Retrieval Augmentation for Commonsense Reasoning: A Unified Approach](https://arxiv.org/pdf/2210.12887.pdf)
    - BLEU (BL-4)
    - ROUGE (RG-L)
    - METEOR (MET)
- [Is ChatGPT A Good Translator? A Preliminary Study](https://arxiv.org/abs/2301.08745)
    - BLEU
    - ChrF++
    - TER↓
    - LR: length ratio
- [How Good Are GPT Models at Machine Translation? A Comprehensive Evaluation](https://arxiv.org/abs/2302.09210)
    - COMET-22 
    - COMETkiwi
    - Doc-COMETkiwi
    - ChrF 
    - BLEU
