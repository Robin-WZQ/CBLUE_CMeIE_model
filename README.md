# CBLUE_CMeIE_baseline
CBLUE关系抽取模型

## Mission - 任务描述
> 实体和关系抽取作为信息抽取的重要子任务，近些年众多学者利用多种技术在该领域开展深入研究。将这些技术应用于医学领域，抽取非结构化和半结构化的医学文本构建成医学知识图谱，可服务于下游子任务。非结构化的医学文本，如医学教材每一个自然段落，临床实践中每种疾病下的主题，电子病历数据中的主诉、现病史、鉴别诊断等，都是由中文自然语言句子或句子集合组成。实体关系抽取是从非结构化医学文本中找出医学实体，并确定实体对关系事实的过程。

关于任务更详尽的描述可参考比赛链接： [中文医疗信息处理挑战榜](https://tianchi.aliyun.com/dataset/dataDetail?dataId=95414)


## Dataset - 数据集

中文医疗信息处理挑战榜CBLUE 中CMeIE数据集，同样是 CHIP2020/2021 的医学实体关系抽取数据集。

## Enviroment - 环境
- python = 3.8.3
- pytorch = 1.10.0+cu113
- pytorch_pretrained_bert
- tqdm

## Usage - 使用方法

0. 下载本仓库:
    ```Shell
    git clone https://github.com/Robin-WZQ/CBLUE_CMeIE_baseline.git
    cd CBLUE_CMeIE_baseline
    ```

1. 安装依赖:
    ```Shell
    pip install -r requirements.txt
    ```

2. 下载预训练模型

https://drive.google.com/file/d/1eHM3l4fMo6DsQYGmey7UZGiTmQquHw25/view

P.S. 我使用的是Roberta-base(Large太大电脑跑不动了-_-)，也可以使用别的模型。

3.保证目录如下所示：

```
| Chinese_roberta_wwm_ext_pytorch # 中文预训练模型
----| bert_config.json
----| pytorch_model.bin
----| vocab.txt
| CMeIE
----| CMeIE_train.json # 训练集
----| CMeIE_dev.json # 开发集
----| CMeIE_test.json # 测试集
----| README.txt # 数据说明文件
----| schema.json # 关系约束
| record
draw.py # 绘图函数
roberta_base.py # 主函数
README.md # 说明文件
requirements.txt # 配置文件
```

4. 运行
    ```Shell
    run main.py
    ```
5. 生成文件
- roberta.pth # 训练完的模型
- dev_pred.json # 开发集预测结果
- RE_pred.json # 测试集预测结果（提交时需命名为CMeIE_test.jsonl，并压缩后提交）

## Result - 结果
<div align=center>
    <img width="816" alt="pic1" src="https://user-images.githubusercontent.com/60317828/172048567-a631a1bd-8082-4847-b7b8-06f799ecc41c.png">
</div>


## Reference - 参考

https://github.com/CBLUEbenchmark/CBLUE

https://github.com/ymcui/Chinese-BERT-wwm#%E6%A8%A1%E5%9E%8B%E5%AF%B9%E6%AF%94

https://zhuanlan.zhihu.com/p/136277427
