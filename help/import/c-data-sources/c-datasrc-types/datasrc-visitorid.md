---
description: 選取「通用 (交易ID)」類別，可整合訪客 ID。
subtopic: Data sources
title: 訪客 ID
topic-fix: Developer and implementation
feature: Data Sources
exl-id: 940af1ba-0d12-4552-a21e-0ceb06427ab2
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: ht
source-wordcount: '224'
ht-degree: 100%

---

# VisitorID

可透過選取[!UICONTROL 呼叫中心資料]類別來整合訪客 ID。

請參閱[整合離線資料](/help/import/c-data-sources/datasrc-integrating-offline-data.md)。

## VisitorID 維度

| 欄名稱 | 說明 |
|--- |--- |
| [!UICONTROL VisitorID] | (必要) 獨特值，代表離線和線上系統的客戶。 |
| [!UICONTROL 日期] | 使用以下日期格式：`MM/DD/YYYY/hh/mm/ss` (例如 07/14/2017/06/00/00) |
| [!UICONTROL 追蹤代碼] | 追蹤代碼名稱。 |
| [!UICONTROL 類別] | 類別名稱。若您指定類別，則必須選取產品。 |
| [!UICONTROL 管道] | 管道名稱。 |
| [!UICONTROL eVar ]*n* | eVar *n* 的名稱。*n* 的有效值是整數 1 - 75。 |
| [!UICONTROL 產品] | 產品名稱。 |
| [!UICONTROL 州別] | 州/省名。 |
| [!UICONTROL Zip] | 郵遞區號名稱。 |

## 訪客 ID 量度

| 欄名稱 | 說明 |
| --- | --- |
| [!UICONTROL 點進] | 追蹤代碼檢視次數。 |
| [!UICONTROL 購物車新增次數] | 購物車新增次數。 |
| [!UICONTROL 購物車開啟次數] | 購物車開啟次數。 |
| [!UICONTROL 購物車移除次數] | 購物車移除次數。 |
| [!UICONTROL 購物車檢視] | 購物車檢視次數。 |
| [!UICONTROL 結帳] | 結帳次數。 |
| [!UICONTROL 事件&#x200B;]*n* | 事件&#x200B;*n* 的發生次數。n 的有效值是整數 1 - 100。若您指定「[!UICONTROL 檢視]」事件，則必須指定對應的資料維度 (eVar)。例如，若加入 eVar2 檢視，則必須列出 eVar2 和它的值。 |
| [!UICONTROL eVar ]*n* 檢視 | 檢視 eVar *n* 的次數。*n* 的有效值是整數 1 - 75。 |
| [!UICONTROL 價格] | 產品價格。 |
| [!UICONTROL 訂購] | 訂購次數。 |
| [!UICONTROL 產品檢視] | 產品檢視次數。 |
| [!UICONTROL 數量] | 售出件數。 |
