---
title: account
description: 使用帳戶變數可判斷資料要傳送至的報表套裝。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# account

> [!IMPORTANT] 此變數已停用。 如果您 [`s.sa()`](../functions/sa-method.md) 的實作需要修改報表套裝目標，請使用函式。

在舊版Adobe Analytics中，變數會 `account` 決定您要傳送資料的報表套裝。 必須有報表套裝ID才能傳送資料至Adobe Analytics。

* 如果您使用Adobe Experience Platform Launch，在設定Adobe Analytics擴充功能時，報 [!UICONTROL Library Management] 表套裝會位於accordion下方。
* 如果您使用 [`s_gi()`](../functions/s-gi.md) 函式實例化Analytics追蹤物件，報表套裝ID已作為函式中的必要引數存在。
