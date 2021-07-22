---
title: 在Adobe Experience Platform中使用標籤實作
description: 了解如何使用標籤實作Adobe Analytics
exl-id: 52990731-8a68-4779-ad42-6ec94b0aabd1
source-git-commit: 5368e808a862a3e320f5d079433db96ab79b45c8
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 43%

---

# 在Adobe Experience Platform中使用標籤實作

>[!NOTE]
>Adobe Experience Platform Launch已重新命名為Experience Platform中的資料收集技術套件。 因此，產品檔案中已推出數個術語變更。 有關術語更改的綜合參考，請參閱以下[document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)。

在 Adobe Analytics 的期限內，Adobe 提供數種不同的方式，可在您的網站上實施用於資料彙集的程式碼。Adobe目前的建議方法是透過Adobe Experience Platform中的標籤。

Adobe Experience Platform中的標籤是標籤管理解決方案，可讓您部署Analytics程式碼及滿足其他標籤需求。 Adobe 可與其他解決方案和產品整合，且您可部署自訂程式碼。您不需依賴組織內部的任何開發團隊更新網站上的程式碼，便可完成上述所有工作。

具有有效Adobe Experience Cloud合約的所有客戶都可使用標籤。 如果您不確定您是否擁有存取權，請聯絡貴組織的任一位 Experience Cloud 系統管理員。

## 整體工作流程

使用標籤來讓實施執行會執行下列步驟：

1. **取得標籤的存取權**:您可以透過組織中的系統管理員取得Platform標籤的存取權。
2. **建立標籤屬性**:屬性是用於參考標籤管理資料的整體容器。
3. **部署至開發環境**：有一個讓您可反覆進行標籤開發程序的環境。
4. **驗證並發佈至生產環境**：確認一切都正常運作，然後發佈使其上線。

請參閱[建立Analytics標籤屬性](create-analytics-property.md)以開始使用。

## 其他資源

標籤可高度自訂。 進一步瞭解如何在實施中加入適當的資料，以充分運用 Adobe Analytics。

* [標籤檔案](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en#):了解介面的運作方式，以及有哪些擴充功能可供使用。
* [Adobe Analytics 擴充功能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=en)：使用 Analytics 擴充功能將資料傳送至 Adobe Analytics。
* [實施變數](../vars/overview.md)：決定您要將哪些變數傳送至資料收集伺服器。
