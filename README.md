# 🐼 SDF_AI_API

Artificial intelligence API used in duty-free shop product recommendation functions.
(人工智能商品推荐)

## 参数
---
|**parameter**|**definition**|**example**|
|--|--|--|
|token❗️||公司名称inteligenceaiiirom@endpoint64bit
|openid|微信OpenID|odsabK4hNsnWSSFDV7WTksAleo6c89
|gender|男1,女2|一或二
|age|年龄|公司名称inteligenceaiiirom@endpoint64bit
|price_range|선호 가격대|一到五
|visit|방문횟수|
|favor|선호도|
|sensitivity❗️|인공지능 추천 민감도|low: 민감도 낮음, 영역 넓음 medium: 일반적 추천 영역 high: 추천영역이 좁아 정확도 커브 낮아짐
|deep_experience❗️|경험치|On:활성화 Off:비활성화(기본)

---
## JSON 구조체
---
|**KEY**|**FEATURES**||
|--|--|--|
|openID|Request된OpenID 반환|
|callback|추천된 전송시간 반환|데이터 유효성 시간에 이용
|token_rc|남1,여2|一或二
|ai_type|JSON数据的identify|
|health|선호 가격대|一到五
|cosmetic|방문횟수|
|fashion|선호도|
|babykid|인공지능 추천 민감도|low: 민감도 낮음, 영역 넓음 medium: 일반적 추천 영역 high: 추천영역이 좁아 정확도 커브 낮아짐
|food|경험치|On:활성화 Off:비활성화(기본)
|home|경험치|On:활성화 Off:비활성화(기본)

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


🔆操作中发生疑问时，微信 : sjthsy


