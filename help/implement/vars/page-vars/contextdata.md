---
title: contextData
description: 上下文資料變數可讓您定義處理規則可讀取之每個頁面上的自訂變數。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# contextData

上下文資料變數可讓您定義處理規則可讀取之每個頁面上的自訂變數。 您可以在上下文資料變數中傳送資料，而不是在程式碼中明確指派值給Analytics變數。 處理規則接著會擷取上下文資料變數值，並將它們傳遞至個別的Analytics變數。 請參閱管理員使用手冊中的[處理規則](/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules.md)。

上下文資料變數有助於開發團隊以命名元素而非編號變數來收集資料。 例如，您可以請求開發團隊將頁面的作者指派給 `eVar10`，而不是指派給頁面的作 `s.contextData["author"]` 者。 然後，您組織中的Analytics管理員可以建立處理規則，將上下文資料變數對應至分析變數，以便進行報告。 開發團隊最終只會擔心上下文資料變數，而不是Adobe提供的許多頁面變數。

## Adobe Experience Platform Launch中的上下文資料變數

Launch沒有專用位置來設定上下文資料變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s.contextData

變 `s.contextData` 數不會直接取值。 請改為將此變數的屬性設為字串。

```js
// Assign the example_variable property a value
s.contextData["example_variable"] = "Example value";
```

* 有效的上下文資料變數只包含英數字元、底線和句點。 如果您包含其他字元（例如連字型大小）,Adobe不保證處理規則中會收集資料。
* 請勿使用啟動上下文資料變數 `"a."`。 此首碼由Adobe保留並使用。 例如，請勿使用 `s.contextData["a.InstallEvent"]`。
* 上下文資料變數不區分大小寫。 變數 `s.contextData["example"]` 和 `s.contextData["EXAMPLE"]` 相同。

## 使用處理規則填入分析變數

> [!IMPORTANT] 處理規則執行後，會捨棄上下文資料變數。 如果您沒有將值放入變數的作用中處理規則，該資料會永久遺失！

1. 更新您的實作以設定上下文資料變數名稱和值。
2. 登入Adobe Analytics並前往「管理>報表套裝」。
3. 選取所要的報表套裝，然後前往「編輯設定>一般>處理規則」。
4. 建立處理規則，將Analytics變數設定為上下文資料變數值。
5. 儲存變更。

處理規則在儲存後立即生效。 它們不適用於歷史資料。

## 在連結追蹤呼叫中傳送上下文資料

將上下文資料變數納入為中的 `contextData` 屬性 [`s.linkTrackVars`](../config-vars/linktrackvars.md):

```js
s.contextData["example_variable"] = "Example value";
s.linkTrackVars = "contextData.example_variable";
s.tl(true,"o","Example context data link");
```
