---
description: 說明如何建立 Data Warehouse 請求的步驟。
title: 設定Data Warehouse請求的報表選項
feature: Data Warehouse
source-git-commit: 6e6a406c7f3ab6ad83dcf60dbd78a5f6953f1fbb
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 18%

---

# 設定Data Warehouse請求的報表選項

>[!AVAILABILITY]
>
>本文中說明的某些Data Warehouse功能(以及本節中的其他Data Warehouse文章)僅在版本的有限測試階段中可用，並且可能在您的環境中尚未提供。
>
>如需關於哪些功能尚未開放所有客戶使用的資訊，以及這些功能發行時間表的相關資訊，請參閱 [發行說明](/help/release-notes/latest.md).
>
>當該功能供一般用途時，此備註將被刪除。有關 Analytics 發佈流程的資訊，請參閱 [Adobe Analytics 功能發佈](/help/release-notes/releases.md)。

建立Data Warehouse請求時，有多種可用的設定選項。 以下資訊說明如何設定請求的報表選項。

如需有關如何開始建立請求的資訊，以及其他重要組態選項的連結，請參閱 [建立Data Warehouse請求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

若要設定Data Warehouse請求的報表選項：

1. 透過選取「 」，開始在Adobe Analytics中建立請求 **[!UICONTROL 工具]** > **[!UICONTROL Data Warehouse]** > [!UICONTROL **新增**].

   如需其他詳細資訊，請參閱 [建立Data Warehouse請求](/help/export/data-warehouse/create-request/t-dw-create-request.md).

1. 在新Data Warehouse請求頁面上，選取 [!UICONTROL **報表選項**] 標籤。

   ![報表目的地索引標籤](assets/dw-report-options.png) <!-- update screenshot to include Sort by metrics -->

1. 填入下列欄位：

   | 選項 | 功能 |
   |---------|----------|
   | [!UICONTROL **檔案名稱**] | 識別報表。 <p>如果檔案名稱中使用了下列任何特殊字元，將無法儲存請求： <code>！ &quot; # $ &amp; &#39; ( ) * + , / : ; > = &lt; ? @ [ ] \ ^ ` {  } \| ~</code> </p><p>%字元後面必須有&quot;R&quot;、&quot;rsid&quot;或&quot;id&quot;，才能使用，如下所示： <code>%R</code>, <code>%rsid</code>、和 <code>%id</code>。</p> |
   | [!UICONTROL **將報表日期範圍附加至檔案名稱**] | 新增日期範圍至報表檔案名稱。 <p>例如，如果您請求從2024年5月1日到2024年5月7日的資料，則檔案名稱包含20240501 - 20240507日期範圍。</p> |
   | [!UICONTROL **CSV**] | 傳送CSV檔案格式的報表，以供在試算表中檢視資料。 |
   | [!UICONTROL **表格(TDE)**] | 傳送Tableau資料擷取(TDE)檔案格式的報告，可用來在Tableau中顯示其他資料中的資料和圖層。 |
   | [!UICONTROL **以壓縮檔案(ZIP)傳送報表**] | 以壓縮(ZIP)檔案格式傳送報表。 我們建議在使用電子郵件作為時啟用此選項 [報告目的地](/help/export/data-warehouse/create-request/dw-request-report-destinations.md). |
   | [!UICONTROL **傳回所有列**] | 啟用時，所有列都會納入報告中。 停用此選項以指定要包含的列數。 |
   | [!UICONTROL **報告評論的開始**] | 新增您要納入報告的任何註解。 註解會顯示在報表的開頭。 |
   | [!UICONTROL **依量度排序**] | 在 Data Warehouse 中提供排名劃分報表，可依遞減的量度順序排序。依量度排序能讓您更容易解讀 Data Warehouse 報表，也更容易將那些報表與其他 Analytics 劃分報告檢視進行比較。<p>如需詳細資訊，請參閱 [依量度排序](/help/export/data-warehouse/sorting-by-metric.md).</p> |
   | [!UICONTROL **傳送資訊清單檔案**] | 包含報表中所包含檔案的中繼資料。<!-- What kind of metadata is included in the manifest file? --> |
   | [!UICONTROL **傳送數位簽名檔案**] | 允許報表收件者確認檔案是否來自Adobe且未曾變更。 |
   | [!UICONTROL **當報告中沒有資料時，傳送空白檔案**] | 即使報表不含任何資料，仍會傳送報表。 |

   {style="table-layout:auto"}

1. 繼續在「 」上設定您的Data Warehouse請求 [!UICONTROL **排程選項**] 標籤。 如需詳細資訊，請參閱 [設定Data Warehouse請求的排程選項](/help/export/data-warehouse/create-request/dw-request-scheduling.md).
