---
title: dynamicAccountSelection
description: dynamicAccountSelection變數會啟用或停用動態帳戶選擇。
translation-type: tm+mt
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountSelection

> [!IMPORTANT] 動態帳戶僅支援使用舊版JavaScript實施（H代碼）。 目前的AppMeasurement程式庫或Adobe Experience Platform Launch不支援這些變數。

變 `dynamicAccountSelection` 數是布林值，可判斷是否使用動態帳戶選擇。

如果設為 `true`,JavaScript檔案會查看 `dynamicAccountMatch` 和 `dynamicAccountList`。

若設為 `false`或未定義此變數，則會忽略 `dynamicAccountMatch` 和 `dynamicAccountList` 變數。

如果未定義此變數，則預設值為 `false`。

## 語法

```js
s.dynamicAccountSelection = [boolean];
```

## 範例

```js
s.dynamicAccountSelection = true;
```
