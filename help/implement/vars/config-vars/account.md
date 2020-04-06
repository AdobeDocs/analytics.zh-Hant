---
title: account
description: 使用 account 變數決定要將資料傳送至哪個報表套裝。
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# account

>[!IMPORTANT] 此變數已淘汰。如果您的實施需要修改報表套裝目的地，請使用 [`s.sa()`](../functions/sa-method.md) 函數。

在舊版 Adobe Analytics 中，`account` 變數會決定您要將資料傳送至哪個報表套裝。必須有報表套裝 ID 才能將資料傳送至 Adobe Analytics。

* If you use Adobe Experience Platform Launch, report suites reside under the [!UICONTROL Library Management] accordion when configuring the Adobe Analytics extension.
* 如果您使用 [`s_gi()`](../functions/s-gi.md) 函數來實例化 Analytics 追蹤物件，報表套裝 ID 已作為函數中的必要引數存在。
