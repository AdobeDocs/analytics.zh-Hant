---
title: dynamicAccountSelection
description: dynamicAccountSelection 變數能啟用或停用動態帳戶選擇。
translation-type: ht
source-git-commit: 4a6cfa479559a644588613bd127c5b45ee8787e6

---


# dynamicAccountSelection

> [!IMPORTANT] 動態帳戶僅支援使用舊版 JavaScript 實施 (H Code)。目前的 AppMeasurement 程式庫或 Adobe Experience Platform Launch 不支援這些變數。

`dynamicAccountSelection` 變數是布林值，可判斷是否使用動態帳戶選擇。

如果設為 `true`，JavaScript 檔案會查看 `dynamicAccountMatch` 和 `dynamicAccountList`。

如果設為 `false` 或未定義此變數，則會忽略 `dynamicAccountMatch` 和 `dynamicAccountList` 變數。

如果此變數未定義，其預設值為 `false`。

## 語法

```js
s.dynamicAccountSelection = [boolean];
```

## 範例

```js
s.dynamicAccountSelection = true;
```
