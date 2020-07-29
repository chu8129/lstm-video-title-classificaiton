## 别指望很详细的描述，坑都是要踩的
## keras配置问题，转原生的tf
        keras使用tf作为backend时lstm爆异常，但无法切换成theano
        使用tf.keras.layer无异常


```
思路:标题类别>>uper类别
```

```
标题类别
fasttext最为方便的工具切结果也不算差，最为推荐
blstm为了测试长短期记忆深度是否有效

由于喜好问题，一般都会吧文本处理成fasttext(baseline)能处理的格式
lstm的脚本也是按fasttext格式读取，经典格式:__label__**


```

```
Model: "sequential"
_________________________________________________________________
Layer (type)                 Output Shape              Param #
=================================================================
embedding (Embedding)        (None, None, 128)         640000
_________________________________________________________________
bidirectional (Bidirectional (None, 256)               263168
_________________________________________________________________
dense (Dense)                (None, 128)               32896
_________________________________________________________________
dense_1 (Dense)              (None, 24)                3096
=================================================================
Total params: 939,160
Trainable params: 939,160
Non-trainable params: 0
_________________________________________________________________
2020-07-22 16:19:27.464208: W tensorflow/core/framework/cpu_allocator_impl.cc:81] Allocation of 648669184 exceeds 10% of free system memory.


数据量：6334660

配置:GeForce GTX 1080 Ti/32G/Intel(R) Core(TM) i7-6700 CPU @ 3.40GHz
一轮:21 minute/19 minute

配置:NULL/128G/Intel(R) Xeon(R) CPU E5-2620 v4 @ 2.10GHz
一轮:2 hour 未结束:20200722 16:41
```

```
好好攒钱买显卡和内存，如果常年用nn
```

```
但：fasttext是真的快并且效果也不差
    fasttext和bert对比情感识别，1%的区别（非极端短的句子）,两个对极端的句子效果均不太好;
    数据来源：常年跑百度的情感接口作为训练验证集，效果是97%和98%的区别
    重点不如放在如何完善训练集和超短文本以及新词发现
```

```
sparse_categorical_crossentropy:,这个loss适合数量较大且不想吧label展开为onehot类型使用
    有个巨坑，lebal转int是从0开始，否则你会发现各种loss=0
    sklearn默认0，keras的Tokenizer是从1开始,如果想要统一用tf内需要自行处理下
```
