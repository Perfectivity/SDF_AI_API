# SDF_AI_API
Artificial intelligence API used in duty-free shop product recommendation functions.
(人工智能商品推荐)

## PARAMETERS
---
|**parameter**|**definition**|**example**|
|--|--|--|
|token❗️|고유번호|公司名称inteligenceaiiirom@endpoint64bit
|openid|wechat|odsabK4hNsnWSSFDV7WTksAleo6c89
|gender|남1,여2|一或二
|age|나이|公司名称inteligenceaiiirom@endpoint64bit
|price_range|선호 가격대|一到五
|visit|방문횟수|
|favor|선호도|
|sensitivity❗️|인공지능 추천 민감도|low: 민감도 낮음, 영역 넓음 medium: 일반적 추천 영역 high: 추천영역이 좁아 정확도 커브 낮아짐
|deep_experience❗️|경험치|On:활성화 Off:비활성화(기본)

---
##JSON 구조체
---
|**KEY**|**FEATURES**||
|--|--|--|
|openID|Request된OpenID 반환|
|callback|추천된 전송시간 반환|데이터 유효성 시간에 이용
|token_rc|남1,여2|一或二
|ai_type|나이|公司名称inteligenceaiiirom@endpoint64bit
|health|선호 가격대|一到五
|cosmetic|방문횟수|
|fashion|선호도|
|babykid|인공지능 추천 민감도|low: 민감도 낮음, 영역 넓음 medium: 일반적 추천 영역 high: 추천영역이 좁아 정확도 커브 낮아짐
|food|경험치|On:활성화 Off:비활성화(기본)
|home|경험치|On:활성화 Off:비활성화(기본)
