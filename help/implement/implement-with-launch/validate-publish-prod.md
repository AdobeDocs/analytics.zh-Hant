---
title: 將Adobe Analytics部署至開發環境
seo-title: 將Adobe Analytics部署至開發環境
description: 瞭解如何使用Adobe Experience Platform Launch將Adobe Analytics部署至您的開發環境。
seo-description: 瞭解如何使用Adobe Experience Platform Launch將Adobe Analytics部署至您的開發環境。
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# 驗證開發實作並發佈至生產環境

當您的Adobe Experience Platform Launch程式庫推送至生產環境後，您的組織就可以開始使用Adobe Analytics來提取基本報表。

## 必備條件

[將Analytics實作部署至您的開發環境](deploy-dev.md)：必須將Analytics實作發佈至您的開發環境，才能遵循此頁面。

## 使用Experience Cloud除錯程式驗證您的開發實作

Experience Cloud除錯程式是Chrome外掛程式，顯示頁面上所有Experience Cloud標記。

1. Open [Chrome Web Browser](https://www.google.com/chrome/) and go to [Adobe Experience Cloud Debugger](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj) on the Chrome Web Store to install the extension.
2. 導覽至您已實施啓動的開發網站。
3. 按一下Chrome右上方的Adobe Experience Cloud除錯程式圖示
4. 如果所有項目都已正確實施，您應該會在Adobe Analytics、Adobe Experience Platform Launch以及Adobe Experience Cloud訪客ID服務中看到內容：

![除錯程式][assets/debugger.png]

## 將開發實作部署至測試/prod

在確認您已看到資料後，就可以將實施推送至網站的即時版本。

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. 按一下您要在網站上實施的Launch屬性。
3. 按一下「發佈」索引標籤，並在開發欄中找到您的程式庫。
4. 按一下程式庫上的下拉式清單，然後選取「提交以供核准」。按一下模式視窗上的「送出」。
5. 再次按一下程式庫的下拉式清單(現在「提交」欄中)，然後選取「建立測試」。
6. 在幾分鐘後，資料庫上的黃色淺色光線變成綠色，表示建立成功。
7. 再次按一下程式庫的下拉式清單，然後選取「核准以進行發佈」。
8. 再次按一下程式庫的下拉式清單(現在位於「核准」欄中)，然後選取「建立並發佈至生產」。
9. 前往「環境」標籤，按一下「生產環境」。
10. 複製生產頁首+頁尾代碼，並將它提供給您的網站擁有者。要求他們在您的網站生產環境上實施此程式碼。

## 驗證您的生產實作

確認您在網站的即時版本中看到資料，並開始為Adobe Analytics進行官方資料收集。

1. 向網站擁有者確認，他們已推送啓動程式碼至生產環境後，請瀏覽至Chrome的首頁，然後開啓Adobe Experience Cloud除錯程式。
2. 如果一切都在運作，您在開發環境中應該會看到類似的資料。此時，您在您的網站上收集資料，現在可以開始使用Adobe Analytics進行報告。

## 疑難排解

**除錯程式中不會顯示任何資料。**

在您的網站上，開啓瀏覽器的開發人員主控台(通常是F12)。查看頁面的原始碼，並確定符合下列項目：

* 主控台中沒有JavaScript錯誤。與您組織的網站擁有者合作，以確保所有JS錯誤都已解決。
* Header code is properly implemented: Make sure the header code is inside the `<head>` tag, and that the file exists.
* AppMeasurement程式庫存在：直接導覽至JS來源，以確定JS檔案包含程式碼。如果沒有，請確定每個環境都已建立，並將程式庫發佈至其個別環境。
* 干擾增效模組：有些Chrome外掛程式可防止影像要求引發。停用任何可能停止資料傳送至Adobe伺服器的外掛程式。

## 後續步驟

現在已設定基本實施，您的組織中的角色可以影響您想要進一步瞭解的路徑：

* [建立解決方案設計文件](../prepare/solution-design.md)：制定您要如何使用自訂變數的計劃，然後將它們包含在您的實施中
* [開始使用分析工作區](../../analyze/analysis-workspace/home.md)：使用工具的旗艦功能直接投入Adobe Analytics。
