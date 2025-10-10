---
title: 動態帳戶概觀
description: 瞭解如何使用 H 程式碼動態選取報表套裝的工作流程。
feature: Implementation Basics
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 100%

---

# 動態帳戶概觀

>[!IMPORTANT]
>
> 動態帳戶僅支援使用舊版 JavaScript 實施作業 (H Code)。目前 AppMeasurement 資料庫或 Adobe Experience Platform 中的標記不支援這些變數。

動態帳戶是一種實施功能，可讓您根據定義的條件決定要使用的報表套裝。如果您的組織需要多個報表套裝，但想要在網站之間使用相同的實施，動態帳戶是個不錯的解決方案。

>[!TIP]
>
>Adobe 建議將資料傳送至單一報表套裝，然後視需要使用虛擬報表套裝來分隔資料。如需詳細資訊，請參閱[全域報表套裝考量事項](../../../prepare/global-rs.md)。

可用來動態選取報表套裝的變數有 3 個。

* [`dynamicAccountSelection`](dynamicaccountselection.md)：啟用或停用動態帳戶選擇。
* [`dynamicAccountMatch`](dynamicaccountmatch.md)：決定要觀察的值，如 URL 或查詢字串。
* [`dynamicAccountList`](dynamicaccountlist.md)：將值與 `dynamicAccountMatch` 比較，如果找到相符項目，系統會填入 `account` 變數。

如果 `dynamicAccountSelection = true`，則會比較 `dynamicAccountMatch` 內的值與 `dynamicAccountList`。如果 `dynamicAccountList` 內的值相符，系統會將報表套裝 ID 納入變數 `account` 中。

## 預設報表套裝

`account` 變數可先行設定，並做為預設值，以備找不到指定的字串時使用。例如：

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

如果 `location.hostname` 不是 `dev.example.com` 或 `example.com`，系統會將點擊傳送至 `examplersiddefault`。

## 多套裝標記

多套裝標記可與動態帳戶選擇搭配使用。例如：

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

如果 `location.hostname` 包含 `example.com`，系統會將點擊傳送至 `examplersid1` 和 `examplersid2` 兩者。
