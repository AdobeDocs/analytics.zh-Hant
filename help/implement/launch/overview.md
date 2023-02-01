---
title: 使用Analytics擴充功能實作Adobe Analytics
description: 了解如何使用標籤和Analytics擴充功能實作Adobe Analytics
feature: Launch Implementation
source-git-commit: e6b40881a543b43c03b612c7e7b0d9bd09f44c0d
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 48%

---

# 使用Analytics擴充功能實作Adobe Analytics

在 Adobe Analytics 的生命週期內，Adobe 提供了數種不同的方式，可在您的網站上實作用於收集資料的程式碼。 Adobe目前的建議方法是透過Adobe Experience Platform中的標籤。

Adobe Experience Platform 中的標記是標記管理解決方案，可讓您部署 Analytics 程式碼以及其他標記需求。 Adobe 可與其他解決方案和產品整合，且您可部署自訂程式碼。您不需依賴組織內部的任何開發團隊更新網站上的程式碼，便可完成上述所有工作。

所有擁有有效 Adobe Experience Cloud 合約的客戶都可以使用標記。 如果您不確定您是否擁有存取權，請聯絡貴組織的任一位 Experience Cloud 系統管理員。

實作工作的概觀：

![Adobe Analytics使用Analytics擴充功能工作流程](../assets/analytics-extension-annotated.png)

|<div style="width:20px"></div>|任務 |更多資訊 | |-| —|—| | 1 |確定您 **定義報表套裝**. | [報表套裝管理器](../../admin/admin/c-manage-report-suites/report-suites-admin.md) | | 2 | **建立資料層** 管理網站上資料的追蹤。 | [建立資料層](../prepare/data-layer.md) | | 3 | **建立標籤屬性**. 屬性是用於參考標籤管理資料的整體容器。| [建立Adobe Analytics標籤屬性](../launch/create-analytics-property.md) | | 4 | **安裝Analytics擴充功能** 在標籤屬性中。 設定Analytics擴充功能以將資料傳送至Adobe Analytics。 | [Adobe Analytics擴充功能概觀](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/client/analytics/overview.html?lang=en) | | 5 | **部署至開發環境**. 有一個環境，讓您可反覆進行標籤開發程式。 | [將Analytics實施部署至開發環境](./deploy-dev.md) | | 6 | **驗證並發佈至生產環境**. 將標籤屬性新增至您的網站。 然後使用資料元素、規則等來自訂您的實作。| [驗證開發實施並發佈至生產環境](./validate-publish-prod.md) |

## 其他資源

標記具有可高度客製化的特性。 進一步了解如何在實作中加入適當的資料，以充分運用 Adobe Analytics。

- [標記文件](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html#)：了解此介面的運作方式以及有哪些可用的擴充功能。

- [實施變數](../vars/overview.md)：決定您要將哪些變數傳送至資料收集伺服器。
