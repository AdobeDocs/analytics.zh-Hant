---
title: 自訂連結
description: 自訂連結的名稱。
feature: Dimensions
exl-id: c153f710-f03f-4be6-8e18-5ebf2ed80f01
source-git-commit: 5c1d50fa09b0fad228f24018de2b062d09b0fe5f
workflow-type: tm+mt
source-wordcount: '242'
ht-degree: 21%

---

# 自訂連結

「自訂連結」[維度](overview.md)會報告您的網站上實作的自訂連結名稱。 自訂連結是一種彈性的追蹤機制，適用於任何非檔案下載或傳出導覽的互動。 常見的範例包括按鈕點按、內部導覽或表單互動。 如果您想要瞭解訪客最常與哪些互動互動，此維度就十分實用。

## 將資料填入此維度中

此維度會根據`pe`查詢字串中的值，從影像要求中的[`pev2`查詢字串](/help/implement/validate/query-parameters.md)收集資料。 `pe`查詢字串決定哪個連結維度會接收`pev2`值：

* **自訂連結** （此頁面）： `lnk_o`
* **[下載連結](download-link.md)**： `lnk_d`
* **[退出連結](exit-link.md)**： `lnk_e`

如果未提供`pev2`，則改用連結URL (`pev1`)作為維度值。 明確提供連結名稱時，最大長度為100個位元組。 衍生自連結URL的值不受此限制。

若要使用AppMeasurement填入此維度，請傳送連結型別引數為`"o"`的[`tl()`](/help/implement/vars/functions/tl-method.md)影像要求。 將連結名稱引數設為所需值：

```js
s.tl(true,"o","Example custom link");
```

## 維度項目

由於此變數以您實施作業中的自訂字串為基礎，因此您的組織會決定維度項目。 Adobe 建議您根據報告需求，將連結分組成有意義的類別。 如果未提供連結名稱，則維度專案會改為顯示為原始URL。 這些原始URL在報表中較難解譯，因此請儘可能提供描述性連結名稱。
