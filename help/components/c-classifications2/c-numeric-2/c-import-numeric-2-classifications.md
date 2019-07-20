---
description: 每個數值 2 分類匯入和匯出檔案皆含有 6 個資料欄。
seo-description: 每個數值 2 分類匯入和匯出檔案皆含有 6 個資料欄。
seo-title: 匯入數值分類
solution: Analytics
subtopic: '分類   '
title: 匯入數值分類
topic: 管理工具
uuid: 82a3034c-e002-4991-900f-22dd45 d54910
translation-type: tm+mt
source-git-commit: 49e149fe57d5d66b8eda22b1bdf60e7c6200761c

---


# 匯入數值分類

>[!IMPORTANT]
>
>匯入數值 2 與日期啟用分類的功能已自基底程式碼移除。此變更預計於 2019 年 7 月維護版本中生效。若您的匯入檔案中含有數值或日期啟用欄，系統會自動忽略這些儲存格，至於該檔案中的其他所有資料都將正常匯入。您仍可透過標準分類工作流程匯出現有分類，並繼續在報表中使用。

每個數值 2 分類匯入和匯出檔案皆含有 6 個資料欄。

以下定義假設您的數值 2 分類名稱為 MyCost。

**~MyCost:** 資料行的描述性名稱。

**~ MyCost^~id~：** 編輯現有列的ID。在新增資料行時，此項目應該是空白的。從「分類管理員」匯出時，系統會自動指定 ID。

**~MyCost^~value~: **The value for the row. 如果比率欄是固定的，此值為分佈整個期間的固定值。如果比率欄是事件，此值為事件的乘數。此項目不能含有逗號。

**~ MyCost^~期間~：** 此列對應的時段。這必須包含開始和結束日期，使用虛線分隔。虛線前後必須加上空格。定義必須使用下列格式:

YYYY/MM/DD - YYYY/MM/DD

**~ MyCost^~rate~：** 由 [!UICONTROL 值] 欄乘以的事件。有效值為:

* fixed - 用來指出值為分佈整個期間的固定值。
* revenue
* order
* unit
* scopen
* scviews
* instance
* click
* checkout
* scadd
* scremove
* event1
* event2
* etc

**~ MyCost^~樞紐~：** 用於在劃分期間分發值的事件。This value is often the same as [!UICONTROL ~MyCost^~rate~], unless you are using [!UICONTROL fixed]. The valid values for this column are identical to that of [!UICONTROL ~MyCost^~rate~], with the addition of [!UICONTROL none].
