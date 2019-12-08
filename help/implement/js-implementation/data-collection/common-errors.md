---
description: 以下幾節將說明動態帳戶的常見錯誤。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 常見錯誤
topic: Developer and implementation
uuid: 04345355-60cc-4678-81c3-390c86752df1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 常見錯誤

以下幾節將說明動態帳戶的常見錯誤。

## 硬式編碼帳戶 {#section_FB6F89BF317F45D387C00986ACA690BC}

若是一律要將資料傳送至特定報表套裝，請將 [!UICONTROL s_dynamicAccountSelection] 設為 false (或者，請完全移除變數): 

```js
var s_account="defaultreportsuiteid" 
REMOVE: s.dynamicAccountSelection=true 
REMOVE: s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
```

在上述案例中，當其他兩行移除後，將一律會使用 defaultreportsuiteid。

## 放置程式碼 {#section_05375CB2EF5A414794BC8209C906AEEB}

在程式碼行後面定義 *`s_account`* 並不會覆寫動態帳戶選項，如下所示。

```js
var s_account="defaultreportsuiteid" 
s.dynamicAccountSelection=true 
s.dynamicAccountList="devreportsuite1=qa.client.com;reportsuite1=client.com" 
s_account="anotherreportsuiteid" 
```

在上述範例中，帳戶 "anotherreportsuiteid" 覆寫了 "defaultreportsuiteid"，但並未覆寫任何出現在 [!UICONTROL s.dynamicAccountList] 中的相符項目。評估 [!UICONTROL s.dynamicAccountList] 的函數實際上要到頗長一段時間後才會在 .JS 檔案中執行。

## 多套裝標記 {#section_6C014FA9B87D4622B483BCDE4281D2A9}

多套裝標記可與動態帳戶選項搭配使用，如下所示。

```js
s.dynamicAccountSelection=true 
s.dynamicAccountList="suiteid1,suiteid2=client.com" 
```

## 動態帳戶比對 {#section_647AB47B38D640D6BCC853FDA4E4342D}

請不要為[!UICONTROL 動態帳戶比對]變數加上引號。其選項顯示如下。

| 主機/網域名稱 | 無 |
|---|---|
| 查詢字串 | s.dynamicAccountMatch=(window.location.search?window.location.search:"?") |
| 主機/網域和路徑 | s.dynamicAccountMatch=window.location.host+window.lcation.pathname |
| 路徑和查詢字串 | s.dynamicAccountMatch=window.location.pathname+(window.location.search?window.location.search""?") |
| 完整 URL | s.dynamicAccountMatch=window.location.href |

