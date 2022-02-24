---
title: 使用 Adobe Experience Platform 中的標記實作
description: 了解如何使用標記來實作 Adobe Analytics
feature: Launch Implementation
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '360'
ht-degree: 100%

---

# 使用 Adobe Experience Platform 中的標記實作

>[!NOTE]
>Adobe Experience Platform Launch 已經過品牌重塑，現在是 Experience Platform 中的一套資料收集技術。 因此，所有產品文件中出現了幾項術語變更。 如需術語變更的彙整參考資料，請參閱以下[文件](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)。

在 Adobe Analytics 的生命週期內，Adobe 提供了數種不同的方式，可在您的網站上實作用於收集資料的程式碼。 Adobe 目前的建議方法是透過 Adobe Experience Platform 中的標記。

Adobe Experience Platform 中的標記是標記管理解決方案，可讓您部署 Analytics 程式碼以及其他標記需求。 Adobe 可與其他解決方案和產品整合，且您可部署自訂程式碼。您不需依賴組織內部的任何開發團隊更新網站上的程式碼，便可完成上述所有工作。

所有擁有有效 Adobe Experience Cloud 合約的客戶都可以使用標記。 如果您不確定您是否擁有存取權，請聯絡貴組織的任一位 Experience Cloud 系統管理員。

## 整體工作流程

使用標記讓實作得以運行需遵循以下步驟：

1. **取得標記的存取權**：您可以透過貴組織的系統管理員來取得 Platform 標記的存取權。
2. **建立標記屬性**：屬性是用來參照標記管理資料的總體容器。
3. **部署至開發環境**：有一個讓您可反覆進行標記開發程序的環境。
4. **驗證並發佈至生產環境**：確認一切都正常運作，然後發佈使其上線。

請參閱「[建立 Analytics 標記屬性](create-analytics-property.md)」，以開始使用。

## 其他資源

標記具有可高度客製化的特性。 進一步了解如何在實作中加入適當的資料，以充分運用 Adobe Analytics。

* [標記文件](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en#)：了解此介面的運作方式以及有哪些可用的擴充功能。
* [Adobe Analytics 擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en)：使用 Analytics 擴充功能將資料傳送至 Adobe Analytics。
* [實施變數](../vars/overview.md)：決定您要將哪些變數傳送至資料收集伺服器。
