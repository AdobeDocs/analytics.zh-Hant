---
title: 動態帳戶概觀
description: 瞭解如何使用H代碼動態選取報表套裝的工作流程。
translation-type: tm+mt
source-git-commit: f313fd0c9ffda054a18ad1d457a74602b08e51fa

---


# 動態帳戶概觀

> [!IMPORTANT] 動態帳戶僅支援使用舊版JavaScript實施（H代碼）。 目前的AppMeasurement程式庫或Adobe Experience Platform Launch不支援這些變數。

動態帳戶是一種實作功能，可讓您根據您定義的准則，決定要使用的報表套裝。 如果您的組織需要多個報表套裝，但想要在您的網站之間使用相同的實作，則動態帳戶是一個不錯的解決方案。

> [!TIP] Adobe建議將資料傳送至單一報表套裝，然後視需要使用虛擬報表套裝來分隔資料。 如需詳 [細資訊，請參閱全域報表套裝考量](../../../prepare/global-rs.md) 。

3個變數可用來動態選取報表套裝。

* [`dynamicAccountSelection`](dynamicaccountselection.md):啟用或停用動態帳戶選擇。
* [`dynamicAccountMatch`](dynamicaccountmatch.md):決定要觀察的值。 例如，URL或查詢字串。
* [`dynamicAccountList`](dynamicaccountlist.md):將值與比 `dynamicAccountMatch`較，如果找到相符項目，請填入變 `account` 數。

如 `dynamicAccountSelection = true`果，則會比較 `dynamicAccountMatch` 內的值 `dynamicAccountList`。 如果值符合 `dynamicAccountList` ，報表套裝ID會包含在變數 `account` 中。

## 預設報表套裝

`account` 變數可先行設定，並做為預設值，以備找不到指定的字串時使用。例如:

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

如果 `location.hostname` 不是 `dev.example.com` 或 `example.com`，則會傳送點擊至 `examplersiddefault`。

## 多套裝標記

多套裝標籤可與動態帳戶選擇搭配使用。 例如:

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

如果 `location.hostname` 包 `example.com`含，則點擊會同時傳送至 `examplersid1` 和 `examplersid2`。
