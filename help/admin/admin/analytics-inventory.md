---
description: 使用Analytics詳細目錄
title: Analytics 庫存
feature: Admin Tools
role: Admin
hide: true
hidefromtoc: true
exl-id: 9fc985c8-93d7-4838-9342-72a6268ef96f
source-git-commit: fceb28b7af480e6d87abf09c26f45a7afb2d3270
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 37%

---

# Analytics 庫存 {#analytics-inventory}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory"
>title="Analytics 庫存"
>abstract="此頁面提供您 Adobe Analytics 環境的全面概觀，包括專案和元件的數量、報告套裝、使用者等資訊。當您開始準備升級至 Customer Journey Analytics 時，這些資訊能提供極大幫助。"

<!-- markdownlint-enable MD034 -->

「Analytics詳細目錄」提供您Adobe Analytics環境的完整總覽，包括專案和元件、報表套裝、使用者等數量。 當您開始準備升級至 Customer Journey Analytics 時，這些資訊能提供極大幫助。

此應用程式的目標是協助您回答下列問題：

* 對於您的組織，哪些資產（例如報表套裝、區段、使用者、工作區專案、資料摘要等）需要升級，以及哪些資產可以留在後面？

* 決定需要移轉的資產後：

   * 您應該在此升級之前進行一些資產清理嗎？

   * 您應該將某些資產合併作為流程的一部分嗎？

   * 資產的升級順序應該為何？

   * 您應該先升級哪一組報表套裝？ 上次？

## 權限

在[Adobe Admin Console](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-console/admin-roles-in-analytics)中擁有Adobe Analytics產品管理員許可權的使用者可以使用Analytics詳細目錄。

## 存取Analytics詳細目錄

1. 在&#x200B;**[!UICONTROL 管理員]**&#x200B;功能表中按一下&#x200B;**[!UICONTROL 分析詳細目錄]**。 或前往&#x200B;**[!UICONTROL 所有管理員]** > **[!UICONTROL 分析詳細目錄]**。

![Analytics-Inventory-menu](assets/an-inventory-menu.png)

1. 主畫面會顯示Adobe Analytics環境的完整清查：

   ![主要詳細目錄畫面](assets/an_inventory.png)

>[!IMPORTANT]
>
>   在此初始版本中，您可以檢視Workspace專案、區段、計算量度、進階(Media Analytics)資料和使用者的摘要數字。 目前，唯一可操作的專案是報表套裝。


## 元件 {#components}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-components"
>title="元件"
>abstract="此區段顯示您 Adobe Analytics 環境中存在的專案、區段和計算量度的數量。專案和元件可以遷移至 Customer Journey Analytics。"

<!-- markdownlint-enable MD034 -->

在此初始版本中，您可以檢視Workspace專案、區段和計算量度的摘要詳細目錄編號。 後續版本將可讓您分析這些元件。

## 資料設定和彙集 {#data-config}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-data-config"
>title="資料設定和彙集"
>abstract="此區段顯示您 Adobe Analytics 環境中的報告套裝數量，以及您對串流媒體的存取權。 "

<!-- markdownlint-enable MD034 -->

### 分析報表套裝

1. 若要分析報表套裝並決定要移轉哪些報表套裝，請瀏覽至&#x200B;**[!UICONTROL 資料組態與集合]** > **[!UICONTROL 報表套裝]**，然後按一下&#x200B;**[!UICONTROL 分析]**。

   ![報告套裝清單](assets/an_inv_rs.png)

   | 元素 | 說明 |
   | --- | --- |
   | 名稱 | 報表套裝的名稱 |
   | ID | 報表套裝ID (rsid)。 指定僅能含英數字元的不重複 ID。此 ID 在建立後即無法變更。由 Adobe 設定必要的 ID 首碼，此值無法變更。 |
   | 發生次數 (過去 90 天) |  |
   | 量度 | How |
   | 維度 |  |
   | Analytics for Target (A4T) 已啟用 |  |
   | 行銷管道已啟用 |  |
   | Source聯結器已啟用 | 要關注的 |
   | 行事曆類型 | 如需詳細資訊，請參閱[自訂行事曆](https://experienceleague.adobe.com/en/docs/analytics/admin/admin-tools/manage-report-suites/edit-report-suite/report-suite-general/custom-calendar#) |

1. 請注意……

### 匯出至 CSV

1. 若要將報表套裝清單匯出至.csv檔案，請按一下[匯出至CSV] ****。

1. .csv檔案將會顯示在您的「下載」資料夾中。

1. 在裝置上使用試算表應用程式開啟並儲存。


## 使用者管理 {#user-management}

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="analytics-inventory-user-management"
>title="使用者管理"
>abstract="此區段顯示您 Adobe Analytics 環境中的使用者數量。"

<!-- markdownlint-enable MD034 -->

使用者管理將可在Analytics詳細目錄的最新版本中使用。