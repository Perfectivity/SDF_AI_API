# 🐼 SDF_AI_API

Artificial intelligence API used in duty-free shop product recommendation functions.
(人工智能商品推荐)

## 参数
---
|**parameter**|**definition**|**example**|
|--|--|--|
|token❗️||tk101inteligenceaiiirom@endpoint64bit
|openid|微信OpenID|odsabK4hNsnWSSFDV7WTksAleo6c89
|gender|男1,女2|一或二
|age|年龄|公司名称inteligenceaiiirom@endpoint64bit
|price_range|商品价格范围| 1：0~175元 ，2：175~290元 ， 3:290~583元 ，4:583~1167元，5:1167元以上
|visit|访问次数|
|favor|暂不使用的参数|
|sensitivity❗️|推荐敏感度|low: 低, medium: 默认 high: 高
|deep_experience❗️|经验值|On:活性 Off: 非活性(默认)

---
## 返回的 JSON 数据 
---
|**KEY**|**FEATURES**|**备注**|
|--|--|--|
|openID|要请的OpenID||
|callback|时间|
|token_rc|男1,女2||
|ai_type|JSON数据的identify||
|health|推荐/非推荐的健康食品名称|没有返回的数据时显示为 “ ”|
|cosmetic|推荐/非推荐的化妆品名称|没有返回的数据时显示为 “ ”|
|fashion|推荐/非推荐的时尚杂货名称|没有返回的数据时显示为 “ ”|
|babykid|推荐/非推荐的儿童用品名称|没有返回的数据时显示为 “ ”|
|food|推荐/非推荐的食品名称|没有返回的数据时显示为 “ ”|
|home|推荐/非推荐的家庭用品名称|没有返回的数据时显示为 “ ”|

---
## Category Flag
---
|**商品分类**|**参数**|
|--|--|
|健康食品|health
|化妆品|cosmetic
|时尚杂货|fashion
|儿童用品|babykid
|食品|food
|家庭用品|home

## ai_type
---
|**ai_type**|**参数**|
|--|--|
|推荐产品（来源于小程序）|preference
|推荐产品（正确答案）|standard
|非推荐产品（来源于微信小程序）|unlike
|非推荐产品(正确答案）|unlike_standard

---
# 接口详情

##  1. 推荐产品（来源于小程序）

🟨 Request URL: https://www.ai-model.kr/ai-deep-mind/predict_proba.ai

🟨 调用数据 ： 6个推荐产品 （每个分类中选1个）

返回数据例子 (**POST**)
```json
{
"openid": "aawre2456aa434MMsaaaaaa", 
"callback": "2021-09-00 10:58:16", 
"token_rcv": "OK",
"ai_type": "preference",
"health": "9351915000116", 
"cosmetic":"9351915000127",
"fashion": "9351915000135",
"babykid": "9351915000145",
"food": "9351915000154",
"home": "9351915000162"
}
```

##  2. 推荐产品（正确答案）

🟩 Request URL: https://www.ai-model.kr/ai-deep-mind/predict_standard.ai

🟩 调用数据 ： 12个推荐产品 （每个分类中选2个）

返回数据例子 (**POST**)
```json
{"openid": "aaaaaaaaaaaaaa", 
"callback": "2021-09-00 14:31:26", 
"token_rcv": "OK",
"ai_type": "standard",
"health": [ "9351915000116", "9351915000114" ], 
"cosmetic": [ "9351915000127", "9351915000124" ], 
"fashion": [ "9351915000135" , "9351915000134" ], 
"babykid": [ "9351915000145", "9351915000144" ], 
"food": [ "9351915000154", "9351915000153" ], 
"home": [ "9351915000162", "9351915000161" ]
}
```

**请注意**‼️ ： 审查委员会通过比较跟 1.推荐产品（来源于小程序） 与 2.推荐产品（正确答案）的过程，计算两个数据的类似度。

##  3. 非推荐产品（来源于小程序）

🟦 Request URL: https://www.ai-model.kr/ai-deep-mind/predict_proba_unlike.ai

🟦 调用数据 ： 4个推荐产品

返回数据例子 (**POST**)
```json
{ 
"openid": "aaaaaaaaaaaaaa", 
"callback": "2021-09-00 14:52:20", 
"token_rcv": "OK",
"ai_type": "unlike",
"health": "",
"cosmetic":"9351915000131", 
"fashion": "9351915000142", 
"babykid": "9351915000150", 
"food": "",
"home": "9351915000168" 
}
```


##  4. 非推荐产品（正确答案）

🟪 Request URL: https://www.ai-model.kr/ai-deep-mind/predict_standard_unlike.ai

🟪 调用数据 ： 6个推荐产品 （每个分类中选1个）

返回数据例子 (**POST**)
```json
{
"openid": "aaaaaaaaaaaaaa", 
"callback": "2021-09-00 14:54:15", 
"token_rcv": "OK",
"ai_type": "unlike_standard", 
"health": "9351915000119", 
"cosmetic":"9351915000131", 
"fashion": "9351915000142", 
"babykid": "9351915000150", 
"food": "9351915000159", 
"home": "9351915000168"
}
```

---


🔆操作中发生疑问时，微信 : sjthsy


