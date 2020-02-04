---
title: account
description: 使用帳戶變數可判斷資料要傳送至的報表套裝。
translation-type: tm+mt
source-git-commit: 1f0fd2dcb0454ad9bc2e0c2141b5e17470c6a5de

---


# account

> [!IMPORTANT] 此變數已停用。 如果您 [`s.sa()`](../functions/sa.md) 的實作需要修改報表套裝目標，請使用函式。

在舊版Adobe Analytics中，變數會 `account` 決定您要傳送資料的報表套裝。 必須有報表套裝ID才能傳送資料至Adobe Analytics。

* 如果您使用Adobe Experience Platform Launch，在設定Adobe Analytics擴充功能時，報表套裝會位於「 [!UICONTROL Library Management] 」（資料庫管理）accordion下方。
* 如果您使用 `s_gi()` 函式實例化Analytics追蹤物件，報表套裝ID已作為函式中的必要引數存在。
