---
description: '在「請求精靈: 步驟 1」中，您可以將粒度等級套用至資料請求。「粒度」能指定報表所包含之時間詳細資料的等級。'
title: 粒度
uuid: 948b3ff2-fcff-45fc-9e8c-8a025ac562b1
feature: Report Builder
role: User, Admin
exl-id: 96c3b93a-9adf-4993-b6fc-9146ee5be4bd
source-git-commit: ae6ffed05f5a33f032d0c7471ccdb1029154ddbd
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 100%

---

# 粒度

{{legacy-arb}}

在「請求精靈: 步驟 1」中，您可以將粒度等級套用至資料請求。「粒度」能指定報表所包含之時間詳細資料的等級。

有效值為「小時」、「日」、「週」、「月」、「季」、「年」及「彙總」。

## Report Builder 的粒度處理方式

假設您選擇[!UICONTROL 「月」]粒度，將日期範圍指定為某個月。請求會顯示以整整一個月之資料量為度量的總計。如果請求的日期範圍跨越一季，報表會顯示三張圖表：每個月份一張圖表，或部分圖表。如果今天是 3 月 18 日，選擇上一季會傳回一張 1 月 1 日到 1 月 31 日的圖表、一張 2 月 1 日到 2 月 28 日的圖表，以及一張 3 月 1 日到 3 月 17 日的圖表。
