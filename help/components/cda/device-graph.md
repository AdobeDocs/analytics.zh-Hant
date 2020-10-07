---
title: 裝置圖表
description: 瞭解使用裝置圖形拼接資料的先決條件和限制。
translation-type: tm+mt
source-git-commit: 954927359420cfdb3d0e908758fc36464e15fee5
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 41%

---


# 裝置圖表

跨裝置分析提供兩種不同的方法，將資料結合在一起。 此方法使用Adobe Experience Platform Identity Service Co-op Graph或Private Graph將資料結合在一起。 CDA會定期與裝置圖形通訊，以將裝置連結在一起。

## 合作圖與私人圖的差異

Adobe在ID服務中提供兩種類型的裝置圖形：

* **合作圖**:雜湊裝置ID的儲存庫，任何客戶都可以提供並參考。 由於此類裝置圖表是協作式的，因此通常比對的裝置比私人圖表多。
* **專用圖**:雜湊裝置ID的儲存庫，僅供您的組織參考。

## 裝置圖表的特定先決條件

如果您要使用裝置圖形方法實作跨裝置分析，則需要下列項目。 請與組織內部團隊及 Adobe 客戶經理合作，確保您符合以下所有條件。

>[!IMPORTANT]
>
>若未符合所有必要條件，可能會導致無法啟用跨裝置分析功能，或在連結資料時效果不彰。

* 概述頁面上列出的所 [有先決條件](overview.md)。
* 貴組織必須使用 Adobe Experience Platform Identity Service 合用圖表或專用圖表。請參閱 Device Co-op 使用指南中的[首頁](https://docs.adobe.com/content/help/zh-Hant/device-co-op/using/home.html)。
* 您的實作必須使用最新版的Experience Cloud ID服務。 請參閱 Experience Cloud Identity Sservice 使用指南中的[首頁](https://docs.adobe.com/content/help/zh-Hant/id-service/using/home.html)。大部分使用 Adobe Experience Platform Launch 的實作可能都已部署 ECID。
* Your implementation must call the `setCustomerIDs` function (or SDK equivalent) whenever an individual can be identified, such as when a user logs in or opens an email. 這項要求適用於所有平台，包括行動應用程式在內 (若有使用)。請參閱 Experience Cloud Identity Service 使用指南中的 [`setCustomerIDs`](https://docs.adobe.com/content/help/zh-Hant/id-service/using/id-service-api/methods/setcustomerids.html)。

## 裝置圖表的特定限制

* 不支援舊式 Analytics ID。只會連結具有 Experience Cloud ID 的訪客。
* 如果您的組織使用「私用圖表」，新裝置最多需要24小時的縫合時間。
* 如果您的組織使用Co-op Graph，造訪您網站的新裝置最多需要兩週的時間才能銜接。 CDA 中最近兩週的連結程度通常低於兩週以前的日期範圍。
* 不支援第三方裝置圖形。

## 後續步驟

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).

