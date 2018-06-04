# 前言 ↺

从今年开始，CCL会议将计划同步举办评测活动。笔者这段时间在一创业公司实习，公司也报名参加这个评测，最后实现上就落在我这里，今年的评测任务是阅读理解，名曰《第一届“讯飞杯”中文机器阅读理解评测》。虽说是阅读理解，但事实上任务比较简单，是属于完形填空类型的，即一段材料中挖了一个空，从上下文中选一个词来填入这个空中。最后我们的模型是单系统排名第6，验证集准确率为73.55%，测试集准确率为75.77%，大家可以在这里观摩排行榜。（“广州火焰信息科技有限公司”就是文本的模型）

事实上，这个数据集和任务格式是哈工大去年提出的，所以这次的评测也是哈工大跟科大讯飞一起联合举办的。哈工大去年的论文《Consensus Attention-based Neural Networks for Chinese Reading Comprehension》就研究过另一个同样格式但不同内容的数据集，是用通用的阅读理解模型做的（通用的阅读理解是指给出材料和问题，从材料中找到问题的答案，完形填空可以认为是通用阅读理解的一个非常小的子集）。

虽然，在这次评测任务的介绍中，评测方总有意无意地引导我们将这个问题理解为阅读理解问题。但笔者觉得，阅读理解本身就难得多，这个就一完形填空，只要把它作为纯粹的完形填空题做就是了，所以本文仅仅是采用类似语言模型的做法来做。这种做法的好处是思路简明直观，计算量低（在笔者的GTX1060上可以跑到batch size为160），便于实验。


# 模型 ↺
# CMRC 2017 Datasets

For more information(in Chinese): http://www.hfl-tek.com/cmrc2017/index.html

Thanks to all participants!

## International Standard Language Resource Number (ISLRN)
ISLRN: 451-824-550-408-2

http://www.islrn.org/resources/resources_info/7839/

## Paper

http://www.lrec-conf.org/proceedings/lrec2018/summaries/32.html

## Reference

If you wish to use this data in your research, please cite:

```
@InProceedings{cmrc2017-dataset,
  author = {Yiming Cui ,Ting Liu ,Zhipeng Chen ,Wentao Ma ,Shijin Wang and Guoping Hu},
  title = {Dataset for the First Evaluation on Chinese Machine Reading Comprehension},
  booktitle = {Proceedings of the Eleventh International Conference on Language Resources and Evaluation (LREC 2018)},
  year = {2018},
  month = {may},
  date = {7-12},
  location = {Miyazaki, Japan},
  editor = {Nicoletta Calzolari (Conference chair) and Khalid Choukri and Christopher Cieri and Thierry Declerck and Sara Goggi and Koiti Hasida and Hitoshi Isahara and Bente Maegaard and Joseph Mariani and Hélène Mazo and Asuncion Moreno and Jan Odijk and Stelios Piperidis and Takenobu Tokunaga},
  publisher = {European Language Resources Association (ELRA)},
  address = {Paris, France},
  isbn = {979-10-95546-00-9},
  language = {english}
  }
```

----------------
CMRC 2017 Evaluation Committee
