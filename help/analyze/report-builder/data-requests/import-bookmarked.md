---
description: 現在，所有書籤化報表與儀表板報表都已列為「請求精靈步驟 1」中的維度，並且可匯入作為 Report Builder 請求。
seo-description: 現在，所有書籤化報表與儀表板報表都已列為「請求精靈步驟 1」中的維度，並且可匯入作為 Report Builder 請求。
seo-title: 匯入書簽化報表和控制面板報表
solution: Analytics
title: 匯入書簽化報表和控制面板報表
topic: Report Builder
uuid: 0fddb2e-5db7-4f64-b571-23482ba3606 d
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 匯入書簽化報表和控制面板報表

現在，所有書籤化報表與儀表板報表都已列為「請求精靈步驟 1」中的維度，並且可匯入作為 Report Builder 請求。

當您選取書籤化報表時，「請求精靈」會填入所有定義此書籤化報表的維度和度量。日期範圍、詳細程度及選取的區段也會根據選取的書籤加以更新。。

以下說明「請求精靈步驟 1」如何顯示儀表板及其報表:

![](assets/import_dashboard_reportlet.png)

When you click **[!UICONTROL Retrieve your Dashboards]** or **[!UICONTROL Retrieve your Bookmarks]**, your existing dashboard and/or bookmark data is retrieved and pasted in the worksheet.

>[!NOTE]
>
>在Report Builder中，可用控制面板和書簽的清單僅限於使用者在精靈步驟中選取的報表套裝。相反地，在行銷 Reports &amp; Analytics 中，無論控制面板和書籤使用哪些報表套裝，您可以存取您具有存取權的所有書籤和控制面板。

>[!NOTE]
>
>只有資料匯入，因此書簽中若包含圖表，或控制面板小報告只包含圖表，則只會匯入填入圖表的資料。

一旦您匯入儀表板報表 (或書籤) 建立請求後，請求便會與報表 (或書籤) 的主要維度建立關聯。因此，如果您編輯請求，樹狀檢視就不會再選取儀表板報表樹狀檢視節點 (或書籤節點)，而會選取請求的主要維度。

匯入的書籤小程式會適當地將報表套裝、已選取區段、維度及選取的度量，設定為「Reports &amp; Analytics」書籤中公開的相同參數。

>[!IMPORTANT]
>
>日期範圍將設為相同的日期範圍，但會設為靜態日期範圍-即使此日期範圍是「報告與分析」書簽中的滾動日期範圍。

