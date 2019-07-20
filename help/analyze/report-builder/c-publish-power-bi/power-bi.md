---
description: 'null'
seo-description: 'null'
seo-title: 發佈至Power BI-概述
title: 發佈至Power BI-概述
uuid: ad688817-6e3c-45da-983d-48c123465309
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 發佈至Power BI-概述

Microsoft Power BI 是一套商業分析控制面板，可分析資料及共用分析結果。Adobe Analytics 與 Power BI 整合可讓您將 Microsoft Power BI 內的 Report Builder 分析資料視覺化，並在整個組織中輕鬆共用該資料。

以前，身為分析師的您會將 Report Builder 活頁簿建立排程，以透過電子郵件 (或 FTP) 散佈。現在，您可以讓企業使用者相關人士在各種平台與裝置皆可使用的網頁式環境中，存取 (從其 Power BI 帳戶內部) 精確且最新的資料。

結合 Report Builder 的報表產生功能與 Power BI 的視覺效果功能後，組織中的所有人便能更容易取得資訊。使用 Power Bi，您還可以將 Adobe Analytics 與其他資料來源整合 (例如銷售點、CRM)，以發掘獨特的客戶分析資料、關聯及商機。

![](assets/aaplusbi.png)

與 Adobe Report Builder 整合可讓您

* [將已排程的 Report Builder 活頁簿發佈到 Power BI](../../../analyze/report-builder/whats-new-arb.md#section_21CA66229EC240D49594A9A7D3FBA687)
* [以 Power BI 資料集表格發佈活頁簿中的所有格式化表格](../../../analyze/report-builder/whats-new-arb.md#section_7C54A54E75184DD6BAEF4ACCE241239A)
* [以 Power BI 資料集表格發佈所有 Report Builder 請求](../../../analyze/report-builder/whats-new-arb.md#section_0C26057C7DBB4068A643FDD688F6E463)

## 系統要求 {#section_0B71092D853446F38FA36447DAC0D32B}

* Adobe Report Builder 5.5 [installed](../../../analyze/report-builder/setup/t-install-arb.md#task_0CA66703882F469EB6DBD9298975D6C3)
* 可讓您登入 Power BI 的有效 Microsoft 帳戶

## Publish workbook to Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

已排程的活頁簿為格式化的 Excel 試算表，其中填入來自 Adobe Analytics 的資料，並以定期排程的方式傳送。

**在報告建立工具中發佈活頁簿**

1. 在 Report Builder 中產生活頁簿並加以儲存。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** &gt; **[!UICONTROL New]**.

1. In the Basic Scheduling Wizard, check the box next to **[!UICONTROL Publish Workbook to Microsoft Power BI]**.

   ![](assets/simple-schedule-wizard.png)

1. 指定您的電子郵件並立即傳送，或者指定排程頻率 (每小時、每日等等)。
1. 按一下&#x200B;**[!UICONTROL 「確定」]以發佈。**
1. 系統會要求您登入 Microsoft 帳戶。請提供您的憑證。
1. Report Builder 活頁簿隨即列入排程並發佈至 Power BI。

   在 Report Builder 排程程序使用更新的 Analytics 資料重新整理活頁簿後，透過每個已排程的例項，系統就會將活頁簿發佈至 Microsoft Power BI。

**在Power BI中檢視Report Builder活頁簿資料**

1. 在 Power BI 中，連按兩下[!UICONTROL 「活頁簿」]功能表下的活頁簿。

   ![](assets/workbooks-power-bi.png)

1. 您現在可以檢視活頁簿控制面板資料。  ![](assets/view-data-pbi.png)

1. 您可以接著釘選此活頁簿的某個區域，以將其包含在任何 Power BI 控制面板中。

## Publish all formatted tables in the workbook as Power BI dataset tables {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE]
>
>如果活頁簿包含巨集，將停用「活頁簿中的所有格式化表格將其發佈為Power BI資料集表格」。

您可以只匯入活頁簿中所有格式化表格的內容，而不匯入整個活頁簿。

**使用案例**: 您有 Excel 活頁簿，可從多個 Report Builder 請求帶入資料，也可建立含有大量公式的摘要表格。您可以只將摘要表格匯入 Power BI 中，並為其建立視覺效果。

**在Report Builder中發佈格式化表格**

1. 在 Report Builder 中，產生含有標題列且其後接著一列資料的資料表格。
1. 選取該表格，然後從&#x200B;**[!UICONTROL 「首頁」]功能表選取**[!UICONTROL 「格式化為表格」]。表格依預設會有名稱 (表格 1、表格 2 等等)，但您可以在[!UICONTROL 「設計」]功能中變更表格名稱。

1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** &gt; **[!UICONTROL New]**.

1. In the Basic Scheduling Wizard, click **[!UICONTROL Advanced Scheduling Options]**.
1. In the [!UICONTROL Scheduling Wizard - Advanced], on the **[!UICONTROL Publishing Options]**tab, check the box next to **[!UICONTROL Publish all Formatted Tables as Power BI dataset tables]**.

   ![](assets/advanced-schedule-wizard2.png)

1. (選用) 在 Power BI 中，您可以自訂已發佈資產的名稱。如果您使用版本編號作為活頁簿名稱的一部分 (例如 myworkbook_v1.1.xlsx)，但不希望版本號碼出現在已發佈之 Power BI 資產的名稱中，就可以使用這個方式。這樣做的好處是，當版本號碼改變時，已發佈的資產不會變更。(在這裡檢視[規格](../../../analyze/report-builder/c-publish-power-bi/specifications-limits.md#concept_1B6522B4D7A9482680198F125D94EEFD)。)

**在Power BI中檢視表格資料**

1. In Power BI, go to the **[!UICONTROL Workspaces]** &gt; **[!UICONTROL Datasets]** menu.

   ![](assets/datasets-menu.png)

1. 選取您已發佈的資料集，然後按一下旁邊的[!UICONTROL 「建立報表」]圖示。請注意，表格將會以「欄位」的形式顯示。

   ![](assets/formatted-tables.png)

1. 選取表格以及與其相關的欄。

   ![](assets/view-table-dataset.png)

1. 從[!UICONTROL 「視覺效果」]功能表，您可以選取要在 Power BI 中將表格視覺化的方式。例如，您可以選擇以折線圖呈現資料:

   ![](assets/bi-line-graph.png)

1. 從這裡，您可以透過此資料集表格建立視覺效果。

## Publish all Report Builder requests as Power BI Dataset tables {#section_0C26057C7DBB4068A643FDD688F6E463}

您可以將所有請求轉換成資料集表格，並在這些表格上方建立視覺效果。

>[!IMPORTANT]
>
>如果活頁簿包含100個以上的請求，則只會將前100個請求發佈至Power BI。另外，對於每個發佈至 Power BI 的請求，系統將只會發佈前 10,000 列資料。因此，雖然這些請求會順利透過排程傳遞，但可發佈至 Power BI 的範圍是有限的。

1. 在 Report Builder 中，使用 Report Builder 請求開啟或建立活頁簿。
1. On the Report Builder Toolbar, click **[!UICONTROL Schedule]** &gt; **[!UICONTROL New]**.

1. In the Basic Scheduling Wizard, click **[!UICONTROL Advanced Scheduling Options]**.
1. In the [!UICONTROL Scheduling Wizard - Advanced], on the **[!UICONTROL Publishing Options]**tab, check the box next to **[!UICONTROL Publish all Report Builder Requests as Power BI Dataset Tables]** ![](assets/advanced-schedule-wizard2.png)

1. Click **[!UICONTROL OK]**.

**在Power BI中檢視請求資料**

系統將會以資料集中的表格發佈每個已排程的 Report Builder 請求。每個請求表格皆以請求中的主要維度命名，且具有一個[!UICONTROL 「報表套裝」]和一個[!UICONTROL 「區段」]欄。

1. In Power BI, go to the **[!UICONTROL Workspaces]** &gt; **[!UICONTROL Datasets]** menu.

1. 選取您已發佈的請求，然後按一下旁邊的[!UICONTROL 「建立報表」]圖示。

   請注意，請求會以表格的形式顯示在[!UICONTROL 「欄位」]功能表中。

   ![](assets/published-requests.png)

   >[!NOTE]
   >
   >不論您如何設定報告建立工具請求在工作表中配置(樞紐配置、自訂配置、某些欄不可見)，Report Builder一律會以相同的二維度、單一標題列格式來發佈請求：日期、維度、度量、報表套裝、區段。

1. Also notice that there is an additional table called **[!UICONTROL Legend]**. 如果您從 Report Builder 上下文擷取請求，可能很難記住每個請求各代表什麼。而「圖例」表格的作用就是可讓您看到「表格 ID」中每個請求的名稱。您也可以新增其他「圖例」欄，以便完整檢視請求。

   ![](assets/legend-table.png)

