---
title: 驗證開發實作並發佈至生產環境
description: 了解如何使用 Adobe Experience Platform 標記，將 Adobe Analytics 部署至您的生產環境中。
exl-id: 2f5bcfee-d75e-4dac-bea9-91c6cc545173
source-git-commit: 1a49c2a6d90fc670bd0646d6d40738a87b74b8eb
workflow-type: ht
source-wordcount: '692'
ht-degree: 100%

---

# 驗證開發實作並發佈至生產環境

將您的標記庫推送至生產環境後，貴組織就可以開始使用 Adobe Analytics 來提取基本報表。

>[!NOTE]
>Adobe Experience Platform Launch 已經過品牌重塑，現在是 Experience Platform 中的一套資料收集技術。 因此，所有產品文件中出現了幾項術語變更。 如需術語變更的彙整參考資料，請參閱以下[文件](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)。

## 先決條件

[將 Analytics 實施部署至開發環境](deploy-dev.md)：必須將 Analytics 實施發佈至開發環境才能關注此頁面。

## 使用 Experience Cloud Debugger 驗證開發實施

Experience Cloud Debugger 是顯示存在於頁面上所有 Experience Cloud 標記的 Chrome 外掛程式。

1. 開啟 [Chrome 網頁瀏覽器](https://www.google.com/chrome/)，然後前往 Chrome 線上應用程式商店中的 [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) 以安裝此擴充功能。
2. 瀏覽至您已在上面實作標記的開發網站。
3. 按一下 Chrome 右上角的 Adobe Experience Cloud Debugger 圖示
4. 如果所有項目皆已正確實作，您應該會在 Adobe Analytics、標記及 Adobe Experience Cloud Visitor ID 服務中看到內容：

![除錯工具][assets/debugger.png]

## 將開發實施部署至測試/生產環境

在驗證您可看到資料後，您可以將實施推送至網站的使用中版本。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
1. 按一下您打算在您的網站上實作的標記屬性。
1. 按一下「**[!UICONTROL 發佈]**」索引標籤，然後在開發欄中找出您的資料庫。
1. 按一下資料庫上的下拉式清單，然後選取「**[!UICONTROL 送交審核]**」。 按一下強制回應視窗中的「**[!UICONTROL 提交]**」。
1. 再次按一下資料庫的下拉式清單 (現位於「已提交」欄)，然後選取「**[!UICONTROL 為暫存而建置]**」。
1. 過了一會兒，資料庫上的黃色燈號會變成綠色，表示建置成功。
1. 再按一下資料庫的下拉式清單，然後選取「**[!UICONTROL 核准發佈]**」。
1. 再次按一下資料庫的下拉式清單 (現位於[!UICONTROL 已核准]欄)，然後選取「**[!UICONTROL 建置並發佈至生產環境]**」。
1. 前往「環境」索引標籤，然後按一下「**[!UICONTROL 生產環境]**」。
1. 複製生產環境頁首與頁尾程式碼，然後將其提供給您的網站負責人。請網站負責人在您網站的生產環境上實作此程式碼。

## 驗證生產環境實施

確認您可在您網站的使用中版本上看到資料，然後開始進行 Adobe Analytics 的正式資料收集。

1. 一旦您已確認網站負責人已將標記程式碼推送至生產環境，請在 Chrome 中瀏覽至您的網站首頁，然後開啟 [!UICONTROL Adobe Experience Cloud Debugger]。
2. 如果一切運作正常，則應該會在開發環境的測試中看到類似的資料。此時，您正在網站上收集資料，且現在可以開始使用 Adobe Analytics 來建立報表。

## 疑難排解

**除錯工具中未出現任何資料。**

在您的網站上時，請開啟瀏覽器的開發人員主控台 (通常是 F12)。查看頁面原始碼，並確認是否符合下列要求：

* 主控台中沒有任何 JavaScript 錯誤。與您組織的網站負責人合作，確認所有 JS 錯誤皆已解決。
* 已正確實施頁首程式碼：確認頁首程式碼位於 `<head>` 標記內，且該檔案確實存在。
* AppMeasurement 資料庫確實存在：直接導覽至 JS 原始碼，確認 JS 檔案包含程式碼。若未包含，請確認皆已建立每個環境，並將資料庫發佈至其個別環境。
* 干擾外掛程式：某些 Chrome 外掛程式可能會阻止影像要求引發。停用可能阻止將資料傳送至 Adobe 伺服器的任何外掛程式。

## 後續步驟

現在基本實施作業已設定，您在組織中的角色可影響您想要進一步了解的路徑：

* [建立解決方案設計文件](../prepare/solution-design.md)：建立要如何使用自訂變數的規劃，然後將其納入您的實施
* [Analysis Workspace 快速入門](/help/analyze/analysis-workspace/home.md)：透過工具的旗艦功能，直接開始使用 Adobe Analytics。
