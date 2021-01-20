---
title: 依欄位彙整
description: 了解使用依欄位彙整方式來結合資料的先決條件和限制。
translation-type: tm+mt
source-git-commit: 12c026fec44f2e66e2997e8b338823f2c7d790e4
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 95%

---


# 依欄位彙整

跨裝置分析提供兩種不同的方法，將資料結合在一起。 此方法依賴 Analytics 變數 (例如 [prop](/help/implement/vars/page-vars/prop.md) 或 [eVar](/help/implement/vars/page-vars/evar.md)) 包含人員識別碼。使用該變數當作將裝置連結在一起的基礎。

## 依欄位彙整的專屬必要條件

如果想使用依欄位彙整來實作跨裝置分析，需具備下列條件。請與組織內部團隊及 Adobe 客戶經理合作，確保您符合以下所有條件。

>[!IMPORTANT]
>
>若未符合所有必要條件，可能會導致無法啟用跨裝置分析功能，或在連結資料時效果不彰。

* [概觀頁面](overview.md)上列出的所有必要條件。
* 您的實作必須設定 prop 或 eVar，才能盡可能唯一識別個人身分，例如當使用者登入或開啟電子郵件時。這項要求適用於所有平台，包括行動應用程式在內 (若有使用)。為依欄位彙整進行佈建時，請將所需的識別變數傳達給您的客戶經理。

## 依欄位彙整的專屬限制

* 依欄位彙整在使用者識別率高的報表套裝上效果最佳。如果您的報表套裝識別率或登入率很低，請考慮使用 [Co-op 圖表](device-graph.md)。

## 後續步驟

您的組織達到所有要求並了解相關限制後，就可以開始[設定跨裝置分析](setup.md)。