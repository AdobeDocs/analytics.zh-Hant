---
title: 在 Launch 中建立 Analytics 屬性
description: 使用 Adobe Experience Platform Launch 建立空間來自訂資料收集方式。
translation-type: tm+mt
source-git-commit: 632fa007fecadf01e2cef67fd3c2519799636e46
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 84%

---


# 在 Adobe Experience Platform Launch 中建立 Analytics 屬性

Adobe Experience Platform Launch 是可用來整合網站上的 Experience Cloud 解決方案 (包括 Analytics) 的工具。本頁具體說明 Launch 管理員如何正確設定基本 Adobe Analytics 實施。

## 必要條件

[建立報表套裝](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)：建立可供 Analytics 收集資料的獨立單位

## 建立屬性並安裝重要的擴充功能

屬性是用來管理標籤的普遍容器。擴充功能可讓您安裝產品專屬標籤並加以設定。

1. 前往 [launch.adobe.com](https://launch.adobe.com)，然後在出現提示時登入。
1. 按一下&#x200B;**[!UICONTROL 新建屬性]**。
1. 為屬性命名 (例如您的網站標題)，然後輸入預計實施 Analytics 的網域。按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 按一下您新建立的屬性以輸入其設定。
1. 按一下&#x200B;**[!UICONTROL 擴展]**&#x200B;頁籤，然後按一下&#x200B;**[!UICONTROL 目錄]**。
1. 找到Identity Service，然後按一下&#x200B;**[!UICONTROL Install]**。
1. 所有設定 (包括 Experience Cloud 組織 ID) 皆應已填寫。按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 回到擴充功能目錄中，找到Adobe Analytics，然後按一下「安裝」。****

## 為 Adobe Analytics 建立資料元素

資料元素是網站特定部分的參考，可用來收集變數值。

1. 前往 [launch.adobe.com](https://launch.adobe.com)，然後在出現提示時登入。
1. 按一下您預計在網站上實施的 Launch 屬性。
1. 按一下&#x200B;**[!UICONTROL 資料元素]**&#x200B;頁籤，然後按一下&#x200B;**[!UICONTROL 建立新資料元素]**。
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

1. 前往 [launch.adobe.com](https://launch.adobe.com)，然後在出現提示時登入。
1. 按一下您預計在網站上實施的 Launch 屬性。
1. 按一下「建立新規則&#x200B;**[!UICONTROL 」，並將其命名為`Global Rule`。]**
1. 按一下事件旁的&#x200B;**[!UICONTROL 新增]**，然後輸入下列設定：
   * 擴充功能：核心
   * 事件類型：已載入程式庫 (頁面頂端)
   * 名稱：核心 - 已載入程式庫 (頁面頂端)
   * 訂購：50
1. 按一下&#x200B;**[!UICONTROL 保留變更]**.
1. 在&#x200B;**[!UICONTROL Actions]**&#x200B;下，按一下&#x200B;**[!UICONTROL Add]**，然後輸入以下設定：
   * 擴充功能：Adobe Analytics
   * 動作類型：設定變數
   * 頁面名稱：按一下容器圖示，然後選取 `Page Name` 資料元素。
   * 促銷活動：具有 `cid` 值的查詢參數
1. 按一下&#x200B;**[!UICONTROL 保留變更]**.
1. 按一下動作旁邊的加號以新增其他動作，然後輸入下列設定：
   * 擴充功能：Adobe Analytics
   * 動作類型：傳送信標
   * 名稱：Adobe Analytics - 傳送信標
   * 追蹤：s.t()
1. 按一下&#x200B;**[!UICONTROL 保留變更]**.
1. 確認您已設定事件和兩個動作，然後按一下「儲存」。****

## 文件和其他資源

* [Adobe Analytics 擴充功能文件](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension)：Adobe Experience Platform Launch 中 Adobe Analytics 擴充功能的完整專屬文件。
* [Launch 快速入門](https://docs.adobelaunch.com/getting-started)：Launch 的完整文件，包括更深入的快速入門手冊
* [Adobe Experience Platform Launch 頻道](https://experienceleague.adobe.com/?tag=Launch#recommended/solutions/experience-platform)：透過影片瞭解如何使用 Launch

## 後續步驟

[將 Analytics 實施部署至開發環境](deploy-dev.md)：讓 Analytics 程式碼在測試環境中正常運作。
