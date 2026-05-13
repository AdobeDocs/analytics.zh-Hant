---
description: '在「請求精靈: 步驟 1」中，您可以將顆粒度等級套用至資料請求。 「顆粒度」能指定報表所包含之時間詳細資料的等級。'
title: 顆粒度
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
TQID: https://experienceleague.adobe.com/26j4Fernl4bfuYeyuVVzw1K5hZvNSD6pDUVOfEc0J8s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 162
ht-degree: 64%

---

# 顆粒度

{{legacy-arb}}

在「請求精靈: 步驟 1」中，您可以將顆粒度等級套用至資料請求。 「顆粒度」能指定報表所包含之時間詳細資料的等級。

有效值為小時、日、周、月、季、年和彙總。

## Report Builder 的顆粒度處理方式

假設您選擇[!UICONTROL 「月」]顆粒度，將日期範圍指定為某個月。 要求只會根據一個月的資料顯示量度的總計。 如果請求的日期範圍跨越一季，報表會顯示三張圖表：每個月份一張圖表，或部分圖表。 如果今天是3月18日，則選擇最後一個季度會傳回1月1日至1月31日的數字、2月1日至2月28日的數字以及3月1日至3月17日的最終數字。
