---
description: 搭配 Microsoft Power BI 使用 Report Builder。
title: 發佈至 Power BI - 概觀
feature: Report Builder
role: User, Admin
exl-id: 3464c153-2db5-41af-9e83-da081ec64ad3
TQID: https://experienceleague.adobe.com/cbxgWbtfj-VSPgIoc9WTd3COG8EL6Vg-U-WRv11KZaY
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 1181
ht-degree: 70%

---

# 發佈至 Power BI - 概觀

{{legacy-arb}}

Microsoft Power BI 是一套商業分析儀表板，可分析資料及共用洞察。 Adobe Analytics與Power BI的整合可讓您在Microsoft Power BI中將Report Builder Analytics資料視覺化，並在您的組織中輕鬆共用。

身為分析師，您可使用電子郵件或 ftp 為 Report Builder 活頁簿分發建立排程。 現在，您可以讓企業相關人士在各種平台與裝置皆可使用的網頁式環境中，存取 (從其 Power BI 帳戶內部) 精確且最新的資料。

結合 Report Builder 的報告產生功能與 Power BI 的視覺效果功能後，組織中的所有人便能更容易取得資訊。 使用 Power BI，您還可以將 Adobe Analytics 與其他資料來源整合 (例如銷售點、CRM 來源)，以發掘不重複客戶分析資料、關聯及商機。

![Microsoft Power BI 圖示加上 Adob&#x200B;&#x200B;e Analytics 圖示的圖表。](assets/aaplusbi.png)

## 系統需求 {#section_0B71092D853446F38FA36447DAC0D32B}

* [已安裝](/help/analyze/legacy-report-builder/setup/t-install-arb.md) Adobe Report Builder 5.5
* 可讓您登入 Power BI 的有效 Microsoft 帳戶

## 將活頁簿發佈至 Power BI {#section_21CA66229EC240D49594A9A7D3FBA687}

已排程的活頁簿為格式化的 Excel 試算表，其中填入來自 Adobe Analytics 的資料，並以定期排程的方式分發。

**在 Report Builder 中發佈活頁簿**

1. 在Report Builder中，產生並儲存活頁簿。
1. 在 Report Builder 工具列上，按一下&#x200B;**[!UICONTROL 「排程]** > **[!UICONTROL 新增」]**。

1. 在「基本排程精靈」中，勾選「**[!UICONTROL 將活頁簿發佈至Microsoft Power BI]**」旁的方塊。

   ![Report Builder 排程精靈的螢幕擷圖會顯示選項，以勾選「將活頁簿發佈到 Microsoft Power BI」選項。](assets/simple-schedule-wizard.png)

1. 指定您的電子郵件並立即傳送，或指定排程頻率（每小時、每日等）。
1. 按一下&#x200B;**[!UICONTROL 「確定」]**&#x200B;即可發佈。
1. 系統現在會要求您登入Microsoft帳戶。 提供您的認證。
1. Report Builder活頁簿已排程並發佈至Power BI。

   對於每個已排程的例項，Report Builder排程程式使用更新後的Analytics資料重新整理活頁簿後，活頁簿將會發佈至Microsoft Power BI。

**在 Power BI 中檢視 Report Builder 活頁簿資料**

1. 在 Power BI 中，連按兩下[!UICONTROL 「活頁簿」]功能表下的活頁簿。

   ![Power BI 活頁簿視圖的螢幕擷圖。](assets/workbooks-power-bi.png)

1. 您現在可以檢視活頁簿儀表板資料。  ![活頁簿儀表板資料。](assets/view-data-pbi.png)

1. 您可以接著釘選此活頁簿的某個區域，以將其包含在任何 Power BI 儀表板中。

## 將活頁簿中所有格式化表格以 Power BI 資料集表格形式發佈。 {#section_7C54A54E75184DD6BAEF4ACCE241239A}

>[!NOTE]
>
>如果活頁簿含有巨集，系統將會停用「以 Power BI 資料集表格形式發佈活頁簿中所有格式化表格」功能。

您可以只匯入活頁簿中所有格式化表格的內容，不能匯入整個活頁簿。

**使用案例**：您有 Excel 活頁簿，可從多個 Report Builder 請求帶入資料，也可建立含有大量公式的摘要表格。 您只能將摘要表格匯入Power BI並為其建立視覺效果。

**在 Report Builder 中發佈格式化表格**

1. 在 Report Builder 中，產生含有標題列且其後接著一列資料的資料表格。
1. 選取該表格，然後從[!UICONTROL 「首頁」]功能表選取&#x200B;**[!UICONTROL 「格式化為表格」]**。 表格依預設會有名稱 (表格 1、表格 2 等等)，但您可以在[!UICONTROL 「設計」]功能中變更表格名稱。

1. 在 Report Builder 工具列上，按一下&#x200B;**[!UICONTROL 「排程]** > **[!UICONTROL 新增」]**。

1. 在「基本排程精靈」中，按一下&#x200B;**[!UICONTROL 「進階排程選項」]**。
1. 在[!UICONTROL 「排程精靈 – 進階」]中的&#x200B;**[!UICONTROL 「發佈選項」]**&#x200B;索引標籤上，勾選&#x200B;**[!UICONTROL 「以 Power BI 資料集表格形式發佈所有格式化表格」]**&#x200B;旁邊的核取方塊。

   ![螢幕擷圖顯示「排程精靈 – 進階發佈選項」及「以 Power BI 資料集發佈所有格式化表格」表格。](assets/advanced-schedule-wizard2.png)

1. （選用）您可以在Power BI中自訂已發佈資產的名稱。 如果您將版本設定當作活頁簿名稱的一部分（例如myworkbook_v1.1.xlsx），而且您不希望版本號碼顯示在已發佈Power BI資產的名稱中，這個功能會很有用。 這樣做的好處是，當版本號碼改變時，已發佈的資產不會變更 (您可前往[這裡](/help/analyze/legacy-report-builder/c-publish-power-bi/specifications-limits.md)檢視規格)。

**在 Power BI 中檢視表格資料**

1. 在 Power BI 中，前往&#x200B;**[!UICONTROL 「工作區]** > **[!UICONTROL 資料集」]**&#x200B;功能表。

   ![螢幕擷圖顯示反白顯示「建立」報告的 Power BI 資料集選單。](assets/datasets-menu.png)

1. 選取您已發佈的資料集，然後按一下旁邊的[!UICONTROL 「建立報告」]圖示。 請注意，表格會顯示為「欄位」。

   ![螢幕擷圖顯示已選取的發佈資料集 (以欄位形式列出表格)。](assets/formatted-tables.png)

1. 選取表格以及與其相關的欄。

   ![螢幕擷圖顯示有相關欄的已選取表格](assets/view-table-dataset.png)

1. 從[!UICONTROL 視覺效果]功能表，您可以選取如何在Power BI中將表格視覺化。 例如，您可以選擇以折線圖呈現資料：

   ![螢幕擷圖顯示視覺效果選單和資料線圖。](assets/bi-line-graph.png)

1. 從這裡，您可以透過此資料集表格建立視覺效果。

## 以 Power BI 資料集表格形式發佈所有 Report Builder 請求 {#section_0C26057C7DBB4068A643FDD688F6E463}

您可以將所有請求轉換成資料集表格，並在這些表格上方建立視覺效果。

>[!IMPORTANT]
>
>如果活頁簿含有超過 100 個請求，系統只會將前 100 個請求發佈至 Power BI。 此外，對於發佈至Power BI的每個請求，只會發佈前10,000列資料。 因此，雖然這些請求可透過排程成功傳遞，但發佈至Power BI的範圍有限。

1. 在Report Builder中，開啟或建立包含Report Builder請求的活頁簿。
1. 在 Report Builder 工具列上，按一下&#x200B;**[!UICONTROL 「排程]** > **[!UICONTROL 新增」]**。

1. 在「基本排程精靈」中，按一下&#x200B;**[!UICONTROL 「進階排程選項」]**。
1. 在「[!UICONTROL 排程精靈 – 進階]」中 (在「**[!UICONTROL 發佈選項]**」標籤上)，勾選後述旁邊的核取方塊：**[!UICONTROL 以 Power BI 資料集表格形式發佈所有 Report Builder 請求]** ![螢幕擷圖顯示「排程精靈」反白顯示「以 Power BI 資料集表格形式發佈所有 Report Builder 請求」選項。](assets/advanced-schedule-wizard2.png)

1. 按一下&#x200B;**[!UICONTROL 「確定」]**。

**在 Power BI 中檢視請求資料**

每個已排程的Report Builder請求都會發佈為資料集中的表格。 每個請求表格皆以請求中的主要維度命名，且具有一個[!UICONTROL 「報告套裝」]和一個[!UICONTROL 「區段」]欄。

1. 在 Power BI 中，前往&#x200B;**[!UICONTROL 「工作區]** > **[!UICONTROL 資料集」]**&#x200B;功能表。

1. 選取您已發佈的請求，然後按一下旁邊的[!UICONTROL 「建立報告」]圖示。

   請注意，要求會顯示為[!UICONTROL 欄位]功能表中的表格。

   ![螢幕擷圖顯示以二維單標題列格式發佈的已選取請求。](assets/published-requests.png)

   >[!NOTE]
   >
   >不論如何設定活頁簿中 Report Builder 請求的編排方式 (樞紐配置、自訂配置、隱藏部分欄)，Report Builder 會一律以相同的二維單一標題列格式發佈請求：「日期」、「維度」、「量度」、「報告套裝」、「區段」。

1. 另請注意，有一個名為&#x200B;**[!UICONTROL 圖例]**&#x200B;的額外資料表。 如果您從Report Builder內容中移除請求，可能很難記住每個請求的意思。 例如，圖例表格的用途是顯示「表格ID」底下每個要求的名稱。 您也可以新增其他圖例欄，以完整檢視請求。

   ![螢幕擷圖顯示圖例表格，其中會在表格 ID 下顯示每個請求的名稱。](assets/legend-table.png)
