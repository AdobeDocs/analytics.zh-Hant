---
title: 退出連結
description: 退出連結的名稱。
feature: Dimensions
exl-id: 090d5fee-4b35-4be7-866c-5ef1d1c4c0a6
source-git-commit: 418e8d467ca29267314e14fba99783d0cb3d05a9
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 22%

---

# 退出連結

「退出連結」[維度](overview.md)會報告您的網站上實作的退出連結名稱。 退出連結會追蹤將訪客導覽至離開目前網域的對外點按。 如果您想要瞭解哪些對外連結的點按頻率最高，此維度就十分實用。

## 將資料填入此維度中

此維度會根據`pe`查詢字串中的值，從影像要求中的[`pev2`查詢字串](/help/implement/validate/query-parameters.md)收集資料。 `pe`查詢字串決定哪個連結維度會接收`pev2`值：

* **[自訂連結](custom-link.md)**： `lnk_o`
* **[下載連結](download-link.md)**： `lnk_d`
* **退出連結** （此頁面）： `lnk_e`

如果未提供`pev2`，則改用連結URL (`pev1`)作為維度值。 明確提供連結名稱時，最大長度為100個位元組。 衍生自連結URL的值不受此限制。

若要使用AppMeasurement填入此維度，請傳送連結型別引數為`"e"`的[`tl()`](/help/implement/vars/functions/tl-method.md)影像要求。 將連結名稱引數設為所需值：

```js
s.tl(true,"e","Example exit link");
```

## 維度項目

由於此變數以您實施作業中的自訂字串為基礎，因此您的組織會決定維度項目。 Adobe 建議您根據報告需求，將連結分組成有意義的類別。 如果未提供連結名稱，則維度專案會改為顯示為原始URL。 這些原始URL在報表中較難解譯，因此請儘可能提供描述性連結名稱。
