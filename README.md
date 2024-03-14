# NTU_TMBA
## 簡介
於2022年暑期加入TMBA程式交易部，學習程式交易回測框架，並於期末報告分享台指期CTA交易策略。

## 資料夾說明
* CTA台指期策略專案:    
開發台指期價差策略，並撰寫回測框架檢視策略效益。
* course:   
學習回測框架。	

## 專案說明
[專案簡報](CTA台指期策略/final_report.pdf)


## Demo
```python
from transformers import BertTokenizer, TFBertForSequenceClassification
tokenizer = BertTokenizer.from_pretrained('bert-base-chinese')
test_input_ids = []
test_attention_masks = []

for entry in tqdm(test_data):
    claim = entry['claim']
    encoded = tokenizer.encode_plus()
    test_input_ids.append(encoded['input_ids'])
    test_attention_masks.append(encoded['attention_mask'])

test_input_ids = tf.concat(test_input_ids, axis=0)
test_attention_masks = tf.concat(test_attention_masks, axis=0)

predictions = loaded_model.predict(
    x={'input_ids': test_input_ids, 'attention_mask': test_attention_masks}
)

```
## References
- Mitchell A. Gordon, 2019, [All The Ways You Can Compress BERT](https://mitchgordon.me/machine/learning/2019/11/18/all-the-ways-to-compress-BERT.html)
- Stickland, et al., ICML’19
- Houlsby, et al., ICML’19
