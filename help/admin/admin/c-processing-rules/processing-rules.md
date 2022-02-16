---
description: 處理規則可簡化資料收集，以及管理傳送至報告的內容。
subtopic: Processing rules
title: 處理規則概觀
feature: Processing Rules
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
source-git-commit: 71b3b1937e7fa272f0497008e8e510204bbb4418
workflow-type: tm+mt
source-wordcount: '394'
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

## 處理規則權限 {#section_8A4846688050453784DAE4D89355169A}

管理員有權使用處理規則 **預設**。 管理員也可透過「管理工具」介面將這些權限授予非管理員。如需指示，請參閱 []

![](assets/processing-rules.png)

>[!IMPORTANT]
>
>因為處理規則會永久影響分析資料，所以Adobe強烈建議處理規則管理員在Adobe Analytics接受認證培訓，並熟悉報告套件的所有資料來源（標準網站、移動站點、移動應用、資料插入API等）。 瞭解各種平台中的內容資料變數和標準變數，有助於避免意外刪除或資料修改等情形。

## 使用上下文資料簡化資料收集 {#section_09EEA03612D24C15839631AA9E9668D8}

上下文資料變數是一種僅可用於處理規則的變數類型。 若要使用內容資料變數，需透過實作傳入重要/值資料配對，並使用處理規則擷取標準分析變數中的這些數值。如此可省去程式設計師花時間瞭解哪些 prop 和/或 eVar 應包含哪些值。

```js
s.contextData['author'] = "Robert Munch";
s.contextData['section'] = "Books";
s.contextData['genre'] = "Youth";
```

在代碼中設定後，可以設定處理規則以將值分配給變數。 例如：

1. 地圖 `author` 至 `eVar2`
2. 地圖 `section` 至 `prop1` 和 `eVar3`
3. 如果 `author` 和 `section` 存在，設定 `event5`

請參閱 [上下文資料](/help/implement/vars/page-vars/contextdata.md) 的子版本。

## 使用處理規則來轉換點擊資料和觸發事件 {#section_8284E72E999244E091CD7FB1A22342B6}

處理規則可以監控傳入值，轉換常見的打字錯誤並根據報告資料設定事件。可以複製 prop 至 eVar、可以串連值以用於報告，並可設定事件。

## 在報告中使用上下文資料變數 {#section_BD098BC503024A0B8703596628071134}

在實作中定義上下文資料變數後，必須將其複製至 eVar 等變數，才能用於報告中。

請參閱 [將上下文資料變數複製到eVar](processing-rules-examples/processing-rules-copy-context-data.md) 和 [使用上下文資料變數設定事件](processing-rules-examples/processing-rules-copy-context-data-event.md) 的子菜單。
