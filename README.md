## 别指望很详细的描述，坑都是要踩的
## keras配置问题，转原生的tf


```
标题类别   >>  uper类别
```

```
标题类别
fasttext最为方便的工具切结果也不算差，最为推荐
blstm为了测试长短期记忆深度是否有效
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
一轮:21 minute

配置:NULL/128G/Intel(R) Xeon(R) CPU E5-2620 v4 @ 2.10GHz
一轮:1.5 hour 未结束:20200722 16:41
```

```
好好攒钱买显卡和内存，如果常年用nn
```
