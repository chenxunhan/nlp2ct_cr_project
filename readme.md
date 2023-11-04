使用proprot 来做1200条数据集，然后做论文里的评分，最后对照

# TASK DESCRIPTION
<!-- 使用Prompt，来源[Is ChatGPT A Good Translator? A Preliminary Study](https://arxiv.org/abs/2301.08745)对数据集 zh.source 和 test.true.en，来源[YutongWang1216/CR-NMT/data/cr_testset](https://github.com/YutongWang1216/CR-NMT/tree/main/data/cr_testset)进行翻译，并对翻译结果进行评分，评分指标借鉴[Revisiting Commonsense Reasoning in Machine Translation: Training, Evaluation and Challenge](https://aclanthology.org/2023.acl-long.866/)等 -->
测试指标
用50条数据，一次翻译一个，看下是不是跟现在的结果一样，句子的前半部分一样

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

# ROUGH CODE
做一个GPT翻译任务，给我python代码
dataset/zh.source文件是中文数据集，每一行包含一个中文句子
读取dataset/zh.source文件到一个列表A里
将这个列表每五个句子为一个单位抽取出来形成一个新的 元素为单位列表 的列表B
循环询问GPT问题：“请翻译下面的话为英文：”并附上B中的的每个单位列表(每5句话)
获得GPT的回答，每次回答放在新的列表C中
循环询问知道列表B的内容全部问完
保存C到文件

# CHATGPT API
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