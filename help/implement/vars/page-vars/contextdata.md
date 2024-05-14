---
title: contextData
description: 上下文資料變數可讓您在每個頁面上定義處理規則可讀取的自訂變數。
feature: Variables
exl-id: f2c747a9-1a03-4f9f-8025-9f4745403a81
role: Admin, Developer
source-git-commit: 831df50a9c73522493ed60ce5df51192b6933480
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 79%

---

# contextData

上下文資料變數可讓您在每個頁面上定義處理規則可讀取的自訂變數。您可以在上下文資料變數中傳送資料，而不必在程式碼中明確指派 Analytics 變數的值。處理規則接著會取用上下文資料變數值，再傳遞至個別的 Analytics 變數。請參閱「管理員使用指南」中的[處理規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)。

上下文資料變數有助於開發團隊收集命名元素中的資料，而非編號變數。例如，與其要求開發團隊將頁面的作者指派給 `eVar10`，不如要求將頁面作者指派給 `s.contextData["author"]`。接下來，貴組織中的 Analytics 管理員就可以建立處理規則，將上下文資料變數與分析變數對應，以便進行報告。開發團隊最終只需擔心上下文資料變數，不必擔心 Adobe 提供的許多頁面變數。

## 使用 Web SDK 的內容資料變數

若使用 [**xdm物件**](/help/implement/aep-edge/xdm-var-mapping.md)，所有未對應至Adobe Analytics變數的欄位都會自動納入為內容資料變數。 您也可以使用XDM物件明確設定內容資料。 然後您可以使用 [處理規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) 將內容資料變數指派給所需的Analytics變數。  另請參閱 [將其他XDM欄位對應到Analytics變數](../../aep-edge/xdm-var-mapping.md#mapping-other-xdm-fields-to-analytics-variables) 以取得詳細資訊。

若使用 [**資料物件**](/help/implement/aep-edge/data-var-mapping.md)，所有上下文資料變數都位在 `data.__adobe.analytics.contextData` 做為機碼值組：

```js
alloy("sendEvent", {
  "data": {
    "__adobe": {
      "analytics": {
        "contextData": {
          "example_variable": "Example value",
          "second_example": "Another value"
        }
      }
    }
  }
});
```

此 [處理規則](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md) 介面會顯示 `c.example_variable` 和 `c.second_example` 在適用的下拉式功能表中。

## 使用 Adobe Analytics 擴充功能的內容資料變數

Adobe Experience Platform 資料收集沒有專用位置可設定上下文資料變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.contextData

`s.contextData` 變數不會直接取用值。請改為將此變數的屬性設為字串。

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* 有效的上下文資料變數只包含英數字元、底線和句點。如果您包含其他字元 (如連字號)，Adobe不保證處理規則能收集資料。
* 請勿使用 `"a."` 來啟動上下文資料變數。此首碼由 Adobe 保留使用。例如，請勿使用 `s.contextData["a.InstallEvent"]`。
* 上下文資料變數不區分大小寫。變數 `s.contextData["example"]` 等於 `s.contextData["EXAMPLE"]`。

## 使用處理規則填入分析變數

>[!WARNING]
>
>處理規則執行後，上下文資料變數便會遭到捨棄。如果您沒有將值放入變數的作用中處理規則，該資料將會永久遺失！

1. 請更新您的實施以設定上下文資料變數名稱和值。
2. 登入Adobe Analytics並前往 **[!UICONTROL 管理員]** > **[!UICONTROL 報告]** 套裝。
3. 選取所需的報表套裝，然後前往「 」 **[!UICONTROL 編輯設定]** > **[!UICONTROL 一般]** > **[!UICONTROL 處理規則]**.
4. 建立處理規則，將 Analytics 變數設定為上下文資料變數值。
5. 儲存變更。

處理規則會在儲存後立即生效。它們不適用於歷史資料。

## 在連結追蹤呼叫中傳送上下文資料

請在 [`s.linkTrackVars`](../config-vars/linktrackvars.md) 中將上下文資料變數納入為 `contextData` 的屬性：

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```

## 使用內容資料變數的增加事件

建立處理規則時，您可以為事件指派內容資料變數。

* 如果內容資料變數包含任何類型的文字，事件會增加 1。
* 如果內容資料變數包含整數，事件會增加該整數的數量。

```js
// Assigning this context data variable to an event increments it by one
s.contextData["example_text"] = "Text value";

// Assigning this context data variable to an event increments it by four
s.contextData["example_number"] = "4";
```
