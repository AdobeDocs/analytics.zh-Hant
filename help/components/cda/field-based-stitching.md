---
title: 現場拼接
description: 瞭解使用現場拼接來拼接資料的先決條件和限制。
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 23%

---


# 現場拼接

跨裝置分析提供兩種不同的方法，將資料結合在一起。 此方法依賴Analytics變數(例如 [prop](/help/implement/vars/page-vars/prop.md)[或eVar](/help/implement/vars/page-vars/evar.md))來包含人員識別碼。 它使用該變數做為將裝置連結在一起的基礎。

## 現場拼接的特定先決條件

如果您想要使用欄位式拼接來實作跨裝置分析，則需要下列項目。 請與組織內部團隊及 Adobe 客戶經理合作，確保您符合以下所有條件。

>[!IMPORTANT]
>
> 若未符合所有必要條件，可能會導致無法啟用跨裝置分析功能，或在連結資料時效果不彰。

* 概述頁面上列出的所 [有先決條件](overview.md)。
* 您的實作必須設定prop或eVar，以便盡可能唯一識別個人身分，例如當使用者登入或開啟電子郵件時。 這項要求適用於所有平台，包括行動應用程式在內 (若有使用)。在為「欄位式」聯繫布建時，將所要的識別變數傳達給您的「帳戶管理員」。

## 欄位式拼接的特定限制

* 現場拼接在具有高使用者識別率的報表套裝上效果最佳。 如果您的報表套裝識別碼或登入率較低，請考慮使 [用Co-op圖表](device-graph.md)。

## 後續步驟

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).