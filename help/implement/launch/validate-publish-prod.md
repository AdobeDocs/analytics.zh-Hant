---
title: 將 Adobe Analytics 部署至開發環境
description: 瞭解如何使用 Adobe Experience Platform Launch 來將 Adobe Analytics 部署至開發環境。
translation-type: ht
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# 驗證開發實施並發佈至生產環境

一旦將 Adobe Experience Platform Launch 程式庫推送至生產環境後，組織就可以開始使用 Adobe Analytics 來提取基本報表。

## 必要條件

[將 Analytics 實施部署至開發環境](deploy-dev.md)：必須將 Analytics 實施發佈至開發環境才能關注此頁面。

## 使用 Experience Cloud Debugger 驗證開發實施

Experience Cloud Debugger 是顯示存在於頁面上所有 Experience Cloud 標籤的 Chrome 外掛程式。

1. 開啟 [Chrome 網頁瀏覽器](https://www.google.com/chrome/)，然後前往 Chrome 線上應用程式商店中的 [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) 以安裝此擴充功能。
2. 導覽至您已實施 Launch 的開發網站。
3. 按一下 Chrome 右上角的 Adobe Experience Cloud Debugger 圖示
4. 如果所有項目皆已正確實施，您應該會在 Adobe Analytics、Adobe Experience Platform Launch 及 Adobe Experience Cloud 訪客 ID 服務中看到內容：

![除錯工具][assets/debugger.png]

## 將開發實施部署至測試/生產環境

在驗證您可看到資料後，您可以將實施推送至網站的使用中版本。

1. 前往 [Adobe Experience Platform Launch](https://launch.adobe.com)，然後在出現提示時登入。
2. 按一下您預計在網站上實施的 Launch 屬性。
3. 按一下「發佈」標籤，然後在開發欄中找出您的程式庫。
4. 按一下程式庫上的下拉式功能表，然後選取送交審核。按一下模組視窗中的提交。
5. 再次按一下程式庫的下拉式功能表 (現位於已提交欄)，然後選取測試建置。
6. 經過一段時間後，程式庫上的黃色燈號會變成綠色，表示建置成功。
7. 再按一下程式庫的下拉式功能表，然後選取核准發佈。
8. 再按一下程式庫的下拉式功能表 (現在位於已核准欄)，然後選取建置並發佈至生產環境。
9. 前往環境標籤，然後按一下「生產環境」。
10. 複製生產環境頁首與頁尾程式碼，然後將其提供給您的網站擁有者。請網站擁有者在您網站的生產環境上實施此程式碼。

## 驗證生產環境實施

確認您可在您網站的使用中版本上看到資料，然後開始進行 Adobe Analytics 的正式資料收集。

1. 一旦您已確認網站擁有者已將 Launch 程式碼推送至生產環境，請在 Chrome 中導覽至您的網站首頁，然後開啟 Adobe Experience Cloud Debugger。
2. 如果一切運作正常，則應該會在開發環境的測試中看到類似的資料。此時，您正在網站上收集資料，且現在可以開始使用 Adobe Analytics 來建立報表。

## 疑難排解

**除錯工具中未出現任何資料。**

在您的網站上時，請開啟瀏覽器的開發人員主控台 (通常是 F12)。查看頁面原始碼，並確認是否符合下列要求：

* 主控台中沒有任何 JavaScript 錯誤。與您組織的網站擁有者合作，確認所有 JS 錯誤皆已解決。
* 已正確實施頁首程式碼：確認頁首程式碼位於 `<head>` 標籤內，且該檔案確實存在。
* AppMeasurement 程式庫確實存在：直接導覽至 JS 原始碼，確認 JS 檔案包含程式碼。若未包含，請確認皆已建立每個環境，並將程式庫發佈至其個別環境。
* 干擾外掛程式：某些 Chrome 外掛程式可能會阻止影像要求引發。停用可能阻止將資料傳送至 Adobe 伺服器的任何外掛程式。

## 後續步驟

現在基本實施已設定完成，您在組織內的角色會影響您要從哪個途徑深入瞭解：

* [建立解決方案設計文件](../prepare/solution-design.md)：建立要如何使用自訂變數的規劃，然後將其納入您的實施
* [Analysis Workspace 快速入門](/help/analyze/analysis-workspace/home.md)：透過工具的旗艦功能，直接開始使用 Adobe Analytics。
