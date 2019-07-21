---
description: 「報表套裝使用量」標籤針對目前使用期間，與您帳單公司綁定的所有登入公司中每個報表套裝提供伺服器使用量資料。
seo-description: 「報表套裝使用量」標籤針對目前使用期間，與您帳單公司綁定的所有登入公司中每個報表套裝提供伺服器使用量資料。
seo-title: 檢視報表套裝使用情形
title: 檢視報表套裝使用情形
uuid: c609ed99-9acc-4023-905a-81a40dd07a79
translation-type: tm+mt
source-git-commit: a6aac17d93877ed2a6525484ba5aa4e741ca116a

---


# 檢視報表套裝使用情形

「報表套裝使用量」標籤針對目前使用期間，與您帳單公司綁定的所有登入公司中每個報表套裝提供伺服器使用量資料。

**[!UICONTROL 「分析]** &gt; **[!UICONTROL 管理]** &gt; **[!UICONTROL 伺服器呼叫使用情形]** &gt; **[!UICONTROL 報表套裝使用情形」]**

>[!IMPORTANT]
>
>If a report suite is not [linked to an Experience Cloud Organization](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html), its usage data will not be reflected in this dashboard. 此外，計費 ID 可以綁定多個 Experience Cloud 組織；組織與計費 ID 之間並非總是 1:1 的關係。

報表套裝使用量控制面板

* 顯示 Experience Cloud 組織中，每個報表套裝之目前使用期間的伺服器呼叫使用量 (所有呼叫、主要、次要、行動主要、行動次要)。
* 顯示每個伺服器呼叫類別的整體使用量百分比。
* 每日更新。
* 可下載。
* 可讓您存取&#x200B;**[!UICONTROL 「管理警報」]UI。**

![](assets/report-suite-usage.png)

| 欄 | 定義 |
|--- |--- |
| 報表套裝名稱 | 報表套裝的易記名稱。 |
| 所有呼叫 (總數 %) | 目前使用期間內發生的所有伺服器呼叫。 |
| 主要呼叫 (%) | 目前使用期間內發生的所有主要伺服器呼叫次數 (及其總計百分比)。 |
| 次要呼叫 (%) | 目前使用期間內發生的所有次要伺服器呼叫次數 (及其總計百分比)。 |
| 主要行動裝置 (%) | 目前使用期間內發生的所有行動主要伺服器呼叫次數 (及其總計百分比)。 |
| 次要行動裝置 (%) | 目前使用期間內發生的所有行動次要伺服器呼叫次數 (及其總計百分比)。 |


## 下載使用情況報表 {#section_D7345660B5E043CD8850954216509A3D}

此選項可讓您下載目前使用資料，以及目前使用期間之前時段的資料 (可追溯至 2015 年 1 月)。該報表將下載為 .csv 檔案。

1. 請選取至少一個報表套裝。
1. Click **[!UICONTROL Download Report]**.

   ![](assets/download_report.png)

| 報表元素 | 說明 |
|--- |--- |
| 檔案名稱 | Hardcoded name: Usage Report `day and time of report creation.csv` |
| 隨附報表套裝 | 您在「報表伺服器使用量」頁面上選取的任何報表套裝都包含在此清單中。 |
| 包含的呼叫類型 | 指定以下任意組合: 所有呼叫 (預設)、主要、次要、行動主要、行動次要。 |
| 時間範圍 | 您可以選擇目前使用期間或指定自訂範圍。對於自訂範圍，請指定「範圍開始」和「範圍結束」。<br>**注意：** 您無法下載2015年月之前的使用資料 </br>。 |

1. Click **[!UICONTROL Download]**.

以下是下載. csv檔案的外觀畫面。它包含報表套裝ID的欄。報表套裝ID指定只能包含英數字元的唯一ID。建立報表套裝後，無法變更此ID。

![](assets/download-usage.png)