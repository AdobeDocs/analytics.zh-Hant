---
description: 處理規則可簡化資料收集，以及管理傳送至報告的內容。
subtopic: Processing rules
title: 處理規則概觀
topic: 管理工具
uuid: 6b4ee7c9-2b86-47a6-b64c-c8d644fff67d
translation-type: tm+mt
source-git-commit: a42fdbf2938f08ab09f9be7e0e3e89bab4f50eae
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 68%

---


# 處理規則概觀

處理規則可簡化資料收集，以及管理傳送至報告的內容。處理規則可以簡化與 IT 團隊以及網頁開發人員之間的互動，提供介面給您進行下列工作：

* 在產品概述頁面中設定事件
* 以查詢字串參數填入促銷活動
* 在 prop 中串連類別和頁面名稱，以進行更簡易報告
* 將 eVar 複製至 Prop 以查看路徑
* 清除拼寫錯誤的網站區段
* 從查詢字串提取內部搜尋詞或促銷活動 ID 以填入 eVar

>[!VIDEO](https://video.tv.adobe.com/v/26124/?quality=12&learn=on)

## 處理規則權限{#section_8A4846688050453784DAE4D89355169A}

管理員依預設有權使用處理規則&#x200B;**。**&#x200B;管理員也可透過「管理工具」介面將這些權限授予非管理員。如需指示，請參閱 []

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>由於處理規則會永久影響Analytics資料，Adobe強烈建議處理規則管理員在Adobe Analytics中接受認證訓練，並熟悉您報表套裝的所有資料來源（標準網站、行動網站、行動應用程式、資料插入API等）。 瞭解各種平台中的內容資料變數和標準變數，有助於避免意外刪除或資料修改等情形。

## 使用上下文資料簡化資料收集 {#section_09EEA03612D24C15839631AA9E9668D8}

上下文資料變數是一種變數，僅適用於處理規則。 若要使用內容資料變數，需透過實作傳入重要/值資料配對，並使用處理規則擷取標準分析變數中的這些數值。如此可省去程式設計師花時間瞭解哪些 prop 和/或 eVar 應包含哪些值。

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

在程式碼中設定後，您就可以設定處理規則來指派值給變數。 例如：

1. 將`author`映射至`eVar2`
2. 將`section`映射至`prop1`和`eVar3`
3. 如果`author`和`section`存在，請設定`event5`

如需詳細資訊，請參閱實作使用指南中的[contextData](/help/implement/vars/page-vars/contextdata.md)。

## 使用處理規則來轉換點擊資料和觸發事件 {#section_8284E72E999244E091CD7FB1A22342B6}

處理規則可以監控傳入值，轉換常見的打字錯誤並根據報告資料設定事件。可以複製 prop 至 eVar、可以串連值以用於報告，並可設定事件。

## 在報告中使用上下文資料變數  {#section_BD098BC503024A0B8703596628071134}

在實作中定義上下文資料變數後，必須將其複製至 eVar 等變數，才能用於報告中。

如需詳細資訊，請參閱[將上下文資料變數複製至eVar](processing-rules-examples/processing-rules-copy-context-data.md)和[使用上下文資料變數](/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data-event.md)設定事件。
