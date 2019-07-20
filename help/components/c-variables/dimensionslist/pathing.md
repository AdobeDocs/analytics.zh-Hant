---
description: 以路徑分析為基礎的報告群組。技術上而言，路徑表示從一個頁面名稱移至另一個 (從一個值移至另一個) 的過程。
seo-description: 以路徑分析為基礎的報告群組。技術上而言，路徑表示從一個頁面名稱移至另一個 (從一個值移至另一個) 的過程。
seo-title: 路徑分析
solution: Analytics
title: 路徑分析
topic: 報表
uuid: c4ff9fa8-e567-4039-9c86-32800a942 da
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 路徑分析

以路徑分析為基礎的報告群組。技術上而言，路徑表示從一個頁面名稱移至另一個 (從一個值移至另一個) 的過程。

[Analysis Workspace 流量](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/flow.html)可提供更具彈性的路徑選項。

>[!NOTE]
>
>To enable pathing, go to **[!UICONTROL Admin &gt; Report Suites &gt; Edit Settings &gt; Traffic &gt; Traffic Variables]**. 若要在「網站區域」及「伺服器」報表啟用路徑功能，請聯絡客戶服務。

若您需要知道值的收集順序，您就必須對收集這些值的變數啟用路徑功能。依預設會為頁面啟用路徑功能。依預設不會為任何 prop 啟用路徑功能，因為它僅適於特定情況。聯絡客戶服務以啟用 prop 的路徑分析。

>[!NOTE]
>
>在臨機分析中，當您在prop上啓用分類時，所有針對已啓用prop設定的分類都會提供路徑度量。

**範例 - 網站區域的路徑**

為&#x200B;*`s.channel`*&#x200B;變數啟用路徑功能，可讓您追蹤網站訪客在「網站區域」之間移動的情形 (當值變更時)。

![](assets/path_sections.png)

接著，路徑即可用於各種不同的路徑報告 (例如[!UICONTROL 下一個網站區域流程])，而顯示訪客瀏覽頁面群組或網站區域的情形。

![](assets/paths_report.png)

**範例 - 搜尋的路徑**

這種從一個值移至另一個值的相同概念也可套用至其他流量變數，包括&#x200B;*`s.props`*。For example, if you enable pathing for your Internal Search Term *`s.prop`*, you could see the path visitors take through search terms.

**範例 - 根據登入狀態的路徑**

您可能會想根據訪客的登入狀態來瞭解他們瀏覽您的網站的路徑。若要檢視這項資訊，您不應在路徑報告中查看登入狀態，因為這些報告所顯示的是訪客在其中變更值的情形，或是訪客如何從登入變更為登出的情形。此時您應連結區段值與&#x200B;*`s.pageName`*&#x200B;變數，然後為產生的變數建立路徑。以下是根據成員狀態來建立頁面路徑的範例程式碼:

```js
s.pageName=“Home Page”; 
s.prop18=“Gold”; // Member Status 
s.prop19=s.prop18 + “:” + s.pageName;
```

接著，請為&#x200B;*`s.prop19`*&#x200B;啟用路徑功能，以檢視成員瀏覽頁面的路徑。

>[!NOTE]
>
>如果執行臨機分析，您可以劃分頁面路徑而無須串連區段值，並將任何區段套用至路徑報表。

