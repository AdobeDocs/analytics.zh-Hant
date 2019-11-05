---
description: 報表中要能顯示渠道和渠道資料，首先須建立渠道和處理資料的基本規則。您亦可建立相關渠道的成本和預算額，並指定所需的訪客參與有效期。報表設定工作在「管理工具」中執行。
seo-description: 報表中要能顯示渠道和渠道資料，首先須建立渠道和處理資料的基本規則。您亦可建立相關渠道的成本和預算額，並指定所需的訪客參與有效期。報表設定工作在「管理工具」中執行。
seo-title: 關於渠道和規則
solution: Analytics
subtopic: 行銷渠道
title: 關於渠道和規則
topic: Reports and Analytics
uuid: 7d574790-4d0d-419d-8fb5-c16ec5a4a387
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# 關於渠道和規則

報表中要能顯示渠道和渠道資料，首先須建立渠道和處理資料的基本規則。您亦可建立相關渠道的成本和預算額，並指定所需的訪客參與有效期。報表設定工作在「管理工具」中執行。

將渠道想像為瀏覽的容器，而規則是為適當的容器指派瀏覽。

![](assets/buckets_2.png)

Adobe 在[自動設定](/help/components/c-marketing-channels/c-channel-autosetup.md)期間提供數個預定義渠道，您可視需求加以編輯。

>[!NOTE]
>
> Adobe建議您在報表套裝中設定報表，以便用作測試的範本。 您可使用範本將渠道和規則設定總體套用至一個或多個生產報表套裝。
>
>請參閱[套用範本報表套裝設定至多個報表套裝](/help/components/c-marketing-channels/t-template.md)。

檢閱下列主題:

* [必備條件](/help/components/c-marketing-channels/c-channels-rules.md#prereqs)
* [重要處理附註](/help/components/c-marketing-channels/c-channels-rules.md#important-proc-rules)

## 必備條件 {#prereqs}

如有必要，請連絡 ClientCare 以協助您釐清這些必要條件:

* In the Administration Console (General Account Settings), enable the **[!UICONTROL Conversion Level]** (e-commerce) option for the report suite.

   See [General Account Settings](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html) in Analytics help for more information.

* Set up user group access to the **[!UICONTROL Marketing Channel Report]**.

   See [Configure User Group Access](/help/components/c-marketing-channels/t-user-groups.md).

* Ensure that your account manager has enabled **[!UICONTROL Channel Reports]** for your report suite.

## Important processing notes {#important-proc-rules}

* 系統以您指定的順序來處理規則，當符合規則後，即停止處理剩餘規則。
* 規則可以存取 VISTA 已設定的變數，但無法存取 VISTA 已刪除的資料。
* 渠道僅儲存轉換量度。流量量度不可用。
* 兩個行銷渠道絕不接收同一事件 (例如購買或點按) 的評分。這將行銷渠道與 eVars (兩個 eVars 可接收同一事件的評分) 區分開來。
* 報表一次最多可處理 25 個渠道。

