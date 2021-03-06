---
title: 裝置圖表
description: 了解使用裝置圖表銜接資料的先決條件和限制。
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: 3f4d8df911c076a5ea41e7295038c0625a4d7c85
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 100%

---

# 裝置圖表

跨裝置分析提供將資料銜接在一起的兩種不同方法。此方法使用 Adobe Experience Platform Identity Service 合用圖表或專用圖表將資料銜接在一起。CDA 會定期與裝置圖表通訊，以將裝置連結在一起。

## 合用圖表與專用圖表的差異

Adobe 在 ID 服務中提供兩種裝置圖表：

* **合用圖表**：雜湊裝置 ID 的存放庫，任何客戶都可以貢獻並參照。由於此類裝置圖表為協作式，因此一般比專用圖表與更多裝置相符。
* **專用圖表**：雜湊裝置 ID 的存放庫，僅供您的組織參照。

## 裝置圖表專屬先決條件

如果您要使用裝置圖表方法實施作業跨裝置分析，須進行下列事項。請與組織內部團隊及 Adobe 客戶經理合作，確保您符合以下所有條件。

>[!WARNING]
>
>若未符合所有先決條件，可能會導致無法啟用跨裝置分析功能，或在連結資料時效果不彰。

* [總覽頁面](overview.md)上列出的所有先決條件。
* 貴組織必須使用 Adobe Experience Platform Identity Service 合用圖表或專用圖表。請參閱 Device Co-op 使用指南中的[首頁](https://experienceleague.adobe.com/docs/device-co-op/using/home.html)。
* 您的實作必須使用最新版本 Experience Cloud ID 服務。請參閱 Experience Cloud Identity Service 使用手冊中的[首頁](https://experienceleague.adobe.com/docs/id-service/using/home.html)。 使用 Adobe Experience Platform 中的標記的大多數實作有可能都已部署 ECID。
* 您的實作必須在可識別個人身分時 (例如使用者登入或開啟電子郵件)，呼叫 `setCustomerIDs` 函式 (或相等 SDK 項目)。這項要求適用於所有平台，包括行動應用程式在內 (若有使用)。請參閱 Experience Cloud Identity Service 使用指南中的 [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html)。

## 裝置圖表專屬限制

* 不支援舊式 Analytics ID。只會連結具有 Experience Cloud ID 的訪客。
* 如果您的組織使用「專屬圖表」，則新裝置最多需要 24 小時的銜接時間。
* 如果您的組織使用「合用圖表」，造訪您網站的新裝置最多需要兩週的銜接時間。CDA 中最近兩週的連結程度通常低於兩週以前的日期範圍。
* 不支援協力廠商裝置圖形。

## 後續步驟

您的組織達到所有要求並了解相關限制後，就可以開始[設定跨裝置分析](setup.md)。
