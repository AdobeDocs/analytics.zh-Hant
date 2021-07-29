---
title: 在標籤中建立Analytics屬性
description: 使用標籤建立空間來自訂資料收集方式。
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: tm+mt
source-wordcount: '608'
ht-degree: 58%

---

# 建立Adobe Analytics標籤屬性

Adobe Experience Platform中的標籤可讓您整合網站上的Experience Cloud解決方案（包括Analytics）。 本頁面具體說明標籤管理員如何正確設定基本Adobe Analytics實作。

>[!NOTE]
>Adobe Experience Platform Launch已重新命名為Experience Platform中的資料收集技術套件。 因此，產品檔案中已推出數個術語變更。 有關術語更改的綜合參考，請參閱以下[document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)。

## 先決條件

[建立報告套裝](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)：建立可供 Analytics 收集資料的獨立單位.

## 建立標籤屬性並安裝重要的擴充功能

屬性是用來管理標籤的普遍容器。擴充功能可讓您安裝產品專屬標籤並加以設定。

1. 使用您的AdobeID憑證登入[資料收集UI](https://experience.adobe.com/data-collection)。
1. 按一下 **[!UICONTROL 新增屬性]**。
1. 為屬性命名 (例如您的網站標題)，然後輸入預計實作 Analytics 的網域。按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 按一下您新建立的標籤屬性以輸入其設定。
1. 按一下&#x200B;**[!UICONTROL 擴充功能]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL 目錄]**。
1. 找到 Identity Service，然後按一下 **[!UICONTROL 安裝]**。
1. 所有設定 (包括 Experience Cloud 組織 ID) 皆應已填寫。按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 返回擴充功能目錄，找到 Adobe Analytics 並按一下&#x200B;**[!UICONTROL 安裝]**。

## 為 Adobe Analytics 建立資料元素

資料元素是網站特定部分的參考，可用來收集變數值。

1. 使用您的AdobeID憑證登入[資料收集UI](https://experience.adobe.com/data-collection)。
1. 按一下您要在網站上實作的標籤屬性。
1. 按一下&#x200B;**[!UICONTROL 資料元素]**&#x200B;標籤，然後按一下&#x200B;**[!UICONTROL 建立新資料元素]**。
1. 為資料元素執行下列設定：

   * 名稱：頁面名稱
   * 擴充功能：核心
   * 資料元素類型：JavaScript 變數
   * 變數路徑：`window.document.title`

      >[!NOTE]
      >
      >此範例值僅供協助您快速上手之用。如果您的組織為頁面名稱定義了更好的值 (例如資料層的值)，您可以在這裡輸入此值。
   * 已勾選簡潔文字
   * 持續時間：Pageview
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 為 Adobe Analytics 建立規則

規則會將資料元素對映至 Analytics 變數值，並決定要在何時將這些值傳送至 Adobe 的伺服器。

1. 使用您的AdobeID憑證登入[資料收集UI](https://experience.adobe.com/data-collection)。
1. 按一下您要在網站上實作的標籤屬性。
1. 按一下&#x200B;**[!UICONTROL 建立新規則]**&#x200B;並命名這新規則`Global Rule`。
1. 按一下事件旁的&#x200B;**[!UICONTROL 新增]**，然後輸入以下的設定值：
   * 擴充功能：核心
   * 事件類型：已載入程式庫 (頁面頂端)
   * 名稱：核心 - 已載入程式庫 (頁面頂端)
   * 訂購：50
1. 按一下&#x200B;**[!UICONTROL 保留變更]**。
1. 在&#x200B;**[!UICONTROL 動作]**&#x200B;項下，按一下&#x200B;**[!UICONTROL 新增]**，然後輸入以下的設定值：
   * 擴充功能：Adobe Analytics
   * 動作類型：設定變數
   * 頁面名稱：按一下容器圖示，然後選取 `Page Name` 資料元素。
   * 促銷活動：具有 `cid` 值的查詢參數
1. 按一下&#x200B;**[!UICONTROL 保留變更]**。
1. 按一下動作旁邊的加號以新增其他動作，然後輸入下列設定：
   * 擴充功能：Adobe Analytics
   * 動作類型：傳送信標
   * 名稱：Adobe Analytics - 傳送信標
   * 追蹤：s.t()
1. 按一下&#x200B;**[!UICONTROL 保留變更]**。
1. 確認已設定好該事件以及兩個動作，然後按一下&#x200B;**[!UICONTROL 儲存]**。

## 文件和其他資源

* [Adobe Analytics擴充功能檔案](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en):標籤中Adobe Analytics擴充功能的完整專屬檔案。
* [標籤快速入門](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=en):標籤的完整檔案，包括更深入的快速入門手冊
* [Adobe Experience Platform Launch頻道](https://experienceleague.adobe.com/?tag=Launch#recommended/solutions/experience-platform):透過影片了解如何使用標籤

## 後續步驟

[將 Analytics 實作部署至開發環境](deploy-dev.md)：讓 Analytics 程式碼在測試環境中正常運作。
