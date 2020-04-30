---
description: 在排程報表時，您可以選擇要用於散佈的發佈清單。
title: 允許發佈清單覆蓋
topic: Report builder
uuid: f2cc9878-ab54-4c6f-8a88-3f3b579955e3
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# 允許發佈清單覆蓋

在排程報表時，您可以選擇要用於散佈的發佈清單。

會在 Analytics 管理工具中設定發佈清單。

請參閱「Analytics 參考」中的[發佈清單管理員](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/publishing-list.html)。

若要啟用此功能，請導覽至視 [!UICONTROL Request Wizard: Step 1] 窗。

If you enable [!UICONTROL Allow Publishing List Override], the report suite assigned to each recipient in the publishing list replaces the report suite for this request. 此外，如果活頁簿含有多個報表套裝，則會使用與發佈清單相關的報表套裝 ID。

此選項不適用於從儲存格選擇的報表套裝。

>[!NOTE]如果將排程報表傳送給多份發佈清單，報表會針對每份清單執行一次。指派給發佈清單的報表套裝軟體會取代變動報表套裝軟體。

