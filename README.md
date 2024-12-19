# Self-RAG
对self-rag的实现的尝试，同时实验一些个人的想法、

主要参考的是[Self-RAG: Learning to Retrieve, Generate, and Critique through Self-Reflection](https://blog.csdn.net/sojrs_sec/article/details/103677940)。

在本项目中，我对原论文中的架构做了进一步的评估实验，以现实该架构的有效性。在实验过程中，发现超参数的配置能很大程度上影响架构的性能，如果超参数配置不合理，甚至会导致架构的性能不如Baseline。此外，即使对每个评估数据集设定了较为合适的超参数，架构的评估结果仍然达不到预期的理想值。我认为可能是数据集中的问题对超参数的需求也存在差异，需要更细粒度地调整。因此，尝试使用提示词工程来针对不同的问题设置不同的超参数，并测试架构在PubHealth数据集上的效果。实验结果显示，模型的表现得到了部分提升，且优于论文中给出的得分，说明该方法存在合理性。由于算力的限制，只能用提示词工程这种简单的方法来模拟，之后还可以采用微调来进一步尝试。

文件说明：
- Self-RAG-intro.md：Self-RAG论文对应的复现方法，需要按照介绍搭建环境，下载检索器和模型。
- Self-RAG-demo.ipynb：自己制作的RAG系统
- short-term-eval.ipynb：更改的short-term tasks和closed-set tasks的评估代码（源代码存在问题，且为了分析PubHealth的错误愿意）
- 其余文件：在Self-RAG的原始代码上进行了修改，包括训练文件和long-term tasks的评估文件



