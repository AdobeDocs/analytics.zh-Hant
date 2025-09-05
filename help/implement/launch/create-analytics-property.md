---
title: 在標記中建立 Analytics 屬性
description: 使用標記建立空間來自訂資料收集的方式。
feature: Tags
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 100%

---

# 建立 Adobe Analytics 標記屬性

Adobe Experience Platform 中的標記可讓您在網站上整合 Experience Cloud 解決方案 (包括 Analytics)。 此頁面會具體說明標記管理員要如何正確地設定基本 Adobe Analytics 實作。

## 先決條件

[建立報表套裝](/help/admin/tools/manage-rs/new-rs/t-create-a-report-suite.md)：為要收集的 Analytics 資料建立一個獨立單位。

## 建立標記屬性，並安裝重要擴充功能

屬性是用來管理標記的普遍容器。擴充功能可讓您安裝產品專屬標記並加以設定。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下 **[!UICONTROL 新增屬性]**。
1. 為屬性命名 (例如您的網站標題)，然後輸入預計實作 Analytics 的網域。按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 按一下您新建立的標記屬性以輸入其設定。
1. 按一下&#x200B;**[!UICONTROL 擴充功能]**&#x200B;標記，然後按一下&#x200B;**[!UICONTROL 目錄]**。
1. 找出「Experience Cloud ID Service」，然後按一下&#x200B;**[!UICONTROL 安裝]**。
1. 所有設定 (包括 Experience Cloud 組織 ID) 皆應已填寫。按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 返回擴充功能目錄，找到 Adobe Analytics 並按一下&#x200B;**[!UICONTROL 安裝]**。

如需更多詳細資訊，請參閱 [Adobe Analytics 擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=zh-Hant)的完整文件。

## 為 Adobe Analytics 建立資料元素

資料元素是網站特定部分的參考，可用來收集變數值。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下您打算在您的網站上實作的標記屬性。
1. 按一下&#x200B;**[!UICONTROL 資料元素]**&#x200B;索引標籤，然後按一下&#x200B;**[!UICONTROL 新增資料元素]**。
1. 為資料元素執行下列設定：

   * 名稱：頁面名稱
   * 擴充功能：核心
   * 資料元素類型：JavaScript 變數
   * JavaScript 變數名稱：`window.document.title`

     >[!NOTE]
     >
     >此值用作協助入門的示例。如果您的組織為頁面名稱定義了更好的值 (例如資料層的值)，您可以在這裡輸入此值。
   * 已勾選簡潔文字
   * 儲存期限：無
1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。

## 為 Adobe Analytics 建立規則

規則會將資料元素對映至 Analytics 變數值，並決定要在何時將這些值傳送至 Adobe 的伺服器。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下您打算在您的網站上實作的標記屬性。
1. 按一下&#x200B;**[!UICONTROL 規則]**&#x200B;索引標籤，然後按一下&#x200B;**[!UICONTROL 新增規則]**。將其重新命名`Global Rule`。
1. 按一下事件旁的&#x200B;**[!UICONTROL 新增]**，然後輸入以下的設定值：
   * 擴充功能：核心
   * 事件類型：已載入資料庫 (頁面頂端)
   * 名稱：核心 - 已載入資料庫 (頁面頂端)
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

## 後續步驟

[將 Analytics 實作部署至開發環境](deploy-dev.md)：讓 Analytics 程式碼在測試環境中正常運作。
