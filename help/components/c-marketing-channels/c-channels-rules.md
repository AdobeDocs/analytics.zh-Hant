---
description: 報表中要能顯示渠道和渠道資料，首先須建立渠道和處理資料的基本規則。您亦可建立相關渠道的成本和預算額，並指定所需的訪客參與有效期。報表設定工作在「管理工具」中執行。
subtopic: Marketing channels
title: 關於渠道和規則
topic: Reports and analytics
uuid: 7d574790-4d0d-419d-8fb5-c16ec5a4a387
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 關於渠道和規則

報表中要能顯示渠道和渠道資料，首先須建立渠道和處理資料的基本規則。您亦可建立相關渠道的成本和預算額，並指定所需的訪客參與有效期。報表設定工作在「管理工具」中執行。

將渠道想像為瀏覽的容器，而規則是為適當的容器指派瀏覽。

![](assets/buckets_2.png)

Adobe 在[自動設定](/help/components/c-marketing-channels/c-channel-autosetup.md)期間提供數個預定義渠道，您可視需求加以編輯。

>[!NOTE]
>
>Adobe 建議在您能作為測試範本使用的報表套裝中設定報表。您可使用範本將渠道和規則設定總體套用至一個或多個生產報表套裝。
>
>請參閱[套用範本報表套裝設定至多個報表套裝](/help/components/c-marketing-channels/t-template.md)。

檢閱下列主題:

* [必備條件](/help/components/c-marketing-channels/c-channels-rules.md#prereqs)
* [重要處理說明](/help/components/c-marketing-channels/c-channels-rules.md#important-proc-rules)

## 必備條件 {#prereqs}

如有必要，請連絡 ClientCare 以協助您釐清這些必要條件:

* 在管理控制台 (一般帳戶設定) 中，啟用報表套裝的&#x200B;**[!UICONTROL 轉換級別]** (電子商務) 選項。

   如需詳細資訊，請參閱 Analytics 說明中的[一般帳戶設定](https://marketing.adobe.com/resources/help/en_US/reference/general_acct_settings_admin.html)。

* 設定使用者群組存取&#x200B;**[!UICONTROL 行銷管道報表]**&#x200B;的權限。

   請參閱[設定使用者群組存取權](/help/components/c-marketing-channels/t-user-groups.md)。

* 確認帳戶管理員已為您的報表套裝啟用&#x200B;**[!UICONTROL 管道報表]**。

## 重要處理說明 {#important-proc-rules}

* 系統以您指定的順序來處理規則，當符合規則後，即停止處理剩餘規則。
* 規則可以存取 VISTA 已設定的變數，但無法存取 VISTA 已刪除的資料。
* 渠道僅儲存轉換量度。流量量度不可用。
* 兩個行銷渠道絕不接收同一事件 (例如購買或點按) 的評分。這將行銷渠道與 eVars (兩個 eVars 可接收同一事件的評分) 區分開來。
* 報表一次最多可處理 25 個渠道。

