从run_glue 文件看起，里面引入了这样一个类 BertForSequenceClassification，

```
class BertForSequenceClassification(BertPreTrainedModel):

##对于这个类说，是对cls的语义表达进行一个线性分类，输入词向量，经过BertModel，生成pooled_output，进行线性分类，损失函数写在了前向函数中。

它的输入是这样的:
input_ids, attention_mask=None, token_type_ids=None,position_ids=None, head_mask=None, labels=None

输出是这样的：
outputs：(loss), logits, (hidden_states), (attentions)
```


看一下BertModel 
```
class BertModel(BertPreTrainedModel):
```


进入bermodel
attention  [batch_size,to_seq_length] 
 [batch_size, 1, 1, to_seq_length]   11111100000
[batch_size, 1, 1, to_seq_length]   00000-1000-1000-1000

[batch_size, num_heads, from_seq_length, to_seq_length]

进入encoder
[batch_size, 1, 1, to_seq_length] 

进入 BertLayer
[batch_size, 1, 1, to_seq_length] 
进入bertattentin
[batch_size, 1, 1, to_seq_length] 
进入bertselfattention

