---
title: 在Launch中建立Analytics屬性
seo-title: 在Adobe Experience Platform Launch中建立Adobe Analytics屬性
description: 使用Adobe Experience Platform Launch建立空間，來自訂資料收集方式。
seo-description: 使用Adobe Experience Platform Launch建立空間，自訂在Adobe Analytics中收集資料的方式。
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 在Adobe Experience Platform Launch中建立Analytics屬性

Adobe Experience Platform Launch是可用來整合Experience Cloud解決方案(包括Analytics)的工具。此頁面概述Launch管理員如何取得正確配置的基本Adobe Analytics實作。

## 必備條件

[建立報表套裝](../../admin/admin-console/create-report-suite.md)：建立要收集Analytics資料的孤島

## 建立屬性並安裝重要擴充功能

屬性是您用來管理標籤的覆蓋容器。擴充功能可讓您安裝產品特定標記並加以設定。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. 按一下「新屬性」。
1. 為您的屬性提供名稱(例如網站的標題)，並輸入您要實施Analytics的網域。按一下「儲存」。
1. 按一下新建立的屬性以輸入其設定。
1. 按一下「延伸模組」標籤，然後按一下「目錄」。
1. 找到Identity Service，然後按一下「安裝」。
1. 所有設定(包括Experience Cloud組織ID)都應該已填妥。按一下「儲存」。
1. 回到擴充功能目錄中，找出Adobe Analytics並按一下「安裝」。

## 建立Adobe Analytics的資料元素

資料元素是網站特定部分的參考，以收集變數值。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
2. 按一下您要在網站上實施的Launch屬性。
3. 按一下「資料元素」標籤，然後按一下「建立新資料元素」。
4. 為資料元素提供下列設定：
   * 名稱：頁面名稱
   * 擴充功能：核心
   * 資料元素類型：JavaScript變數
   * Path to variable: `window.document.title`
      > [!NOTE] 注意：這是協助開始使用的範例值。如果您的組織定義頁面名稱的值較高，例如資料層值，可以在此處輸入。
   * 已勾選清除文字
   * 持續時間：頁面檢視
5. 按一下「儲存」。

## 建立Adobe Analytics的規則

規則會將資料元素對應至Analytics變數值，並判斷這些值何時傳送至Adobe伺服器。

1. Go to [launch.adobe.com](https://launch.adobe.com) and log in if prompted.
1. 按一下您要在網站上實施的Launch屬性。
1. Click Create New Rule and name it `Global Rule`.
1. 按一下事件旁的「新增」，然後輸入下列設定：
   * 擴充功能：核心
   * 事件類型：載入程式庫(頁面頂端)
   * 名稱：核心-載入程式庫(頁面頂端)
   * 訂購：50
1. 按一下「保留變更」。
1. 在「動作」下方，按一下「新增」，然後輸入下列設定：
   * 擴充功能：Adobe Analytics
   * 動作類型：設定變數
   * Page Name: click the container icon, and select the `Page Name` data element.
   * Campaign: Query parameter with a value of `cid`
1. 按一下「保留變更」。
1. 按一下動作旁的加號，新增另一個動作，然後輸入下列設定：
   * 擴充功能：Adobe Analytics
   * 動作類型：傳送信標
   * 名稱：Adobe Analytics-傳送信標
   * 追蹤：s. t()
1. 按一下「保留變更」。
1. 確認您已設定事件和兩個動作，然後按一下「儲存」。

## 說明文件與其他資源

* [Adobe Analytics擴充功能文件](https://docs.adobelaunch.com/extension-reference/web/adobe-analytics-extension)：Adobe Experience Platform Launch中Adobe Analytics擴充功能專屬的完整文件。
* [開始使用Launch](https://docs.adobelaunch.com/getting-started)：適用於Launch的完整文件，包括更深入的入門指南
* [Adobe Experience Platform Launch YouTube頻道](https://www.youtube.com/channel/UCa84ntcvYhPArOBsZIRE2Jw/videos?view=0&shelf_id=0&sort=dd)：瞭解如何透過視訊使用Launch

## 下一步

[將Analytics實作部署至您的開發環境](deploy-dev.md)：取得在測試環境中運作的Analytics程式碼。
