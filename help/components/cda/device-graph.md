---
title: 裝置圖表
description: 了解使用裝置圖表銜接資料的先決條件和限制。
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: f7106ca52447988c90a3ccac6a1e1cc7514f1fc9
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 69%

---

# 裝置圖表

跨裝置分析可使用專用圖表將資料匯整在一起。 專用圖表是貴組織專屬的雜湊裝置ID存放庫。 CDA 會定期與裝置圖表通訊，以將裝置連結在一起。

## 裝置圖表專屬先決條件

如果您要使用裝置圖表方法實施作業跨裝置分析，須進行下列事項。請與組織內部團隊及 Adobe 客戶經理合作，確保您符合以下所有條件。

>[!WARNING]
>
>若未符合所有先決條件，可能會導致無法啟用跨裝置分析功能，或在連結資料時效果不彰。

* [總覽頁面](overview.md)上列出的所有先決條件。
* 您的組織必須使用 [Adobe Experience Platform Identity Service專用圖表](https://business.adobe.com/products/experience-platform/identity-service.html). 另請參閱 [首頁](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=zh-Hant) （在Identity Service使用手冊中）。
* 您的實作必須使用最新版的Experience CloudID服務(ECID)。 請參閱 [首頁](https://experienceleague.adobe.com/docs/id-service/using/home.html) （位於ID服務使用指南中）。 大部分實作使用 [標籤](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=en) 在Adobe Experience Platform中，可能已部署ID服務。
* 您的實作必須在可識別個人身分時 (例如使用者登入或開啟電子郵件)，呼叫 `setCustomerIDs` 函式 (或相等 SDK 項目)。這項要求適用於所有平台，包括行動應用程式在內 (若有使用)。請參閱 [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html) （位於ID服務使用指南中）。

## 裝置圖表專屬限制

* 不支援舊式 Analytics ID。只會連結具有 Experience Cloud ID 的訪客。
* 如果您的組織使用「專屬圖表」，則新裝置最多需要 24 小時的銜接時間。
* 不支援協力廠商裝置圖形。

## 後續步驟

您的組織達到所有要求並了解相關限制後，就可以開始[設定跨裝置分析](setup.md)。
