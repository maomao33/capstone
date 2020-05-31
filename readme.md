# Capstone Project

## 文件结构

`data/` 各种数据

`config/` 模型超参数

`src/` 源代码

`model/` 训练好的模型和日志

[word2vec预训练词向量](https://pan.baidu.com/s/1pUqyn7mnPcUmzxT64gGpSw)，生成的词表已经保存在data文件夹下。

## 数据来源
[THUNews](http://thuctc.thunlp.org/#%E4%B8%AD%E6%96%87%E6%96%87%E6%9C%AC%E5%88%86%E7%B1%BB%E6%95%B0%E6%8D%AE%E9%9B%86THUCNews)的一个子集，从10类新闻中随机抽取了20万条新闻标题，每类各2万条。按照18：1：1划分训练、验证、测试集。


## Performance

以测试集准确率为优化指标。所有的模型都是char-level的，没有分词。

考虑到软硬件的不同，不保证100%可复现，`model`文件夹下载[地址](https://cloud.tsinghua.edu.cn/d/115cba163e02481e9924/)。

| Model    | Acc    |                                                   |
| -------- | ------ | ----------------------------------------------------- |
| fastText (bow) | 90.01% |  |
| fastText(2-gram) | 90.01% |  |
| fastText(3-gram) | 92.54% |  |
| TextCNN | 91.48% |  |
| DPCNN    | 92.00% |  |
| BiLSTM | 91.58% |                                                       |
| BiLSTM with Attention | 91.60% ||
| TextRCNN | 91.79% |                                   |
| BERT-wwm-ext | 94.61% | [来源](https://github.com/ymcui/Chinese-BERT-wwm) |
| RoBERTa-wwm-ext | 94.89% |  |
| TextGCN |  | |

## Usage

将model文件夹解压到根目录后，在src文件夹下运行测试脚本。

```shell
bash test.sh
```

改变json文件中的`load`和`num_epochs`，可以选择是否加载模型和训练的epoch数。
