---
title: account
description: 使用 account 變數決定要將資料傳送至哪個報表套裝。
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
source-git-commit: 3986084eaab81842b6ea0dbabc7bdb78e39f887a
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 80%

---

# 帳戶

>[!IMPORTANT]
>
>此變數已淘汰。如果您的實施需要修改報表套裝目的地，請使用 [`s.sa()`](../functions/sa-method.md) 函數。

在舊版 Adobe Analytics 中，`account` 變數會決定您要將資料傳送至哪個報表套裝。必須有報表套裝 ID 才能將資料傳送至 Adobe Analytics。

* 如果您在Adobe Experience Platform中使用標籤，設定Adobe Analytics擴充功能時，報表套裝位於[!UICONTROL 資料庫管理]折疊式功能表下。
* 如果您使用 [`s_gi()`](../functions/s-gi.md) 函數來實例化 Analytics 追蹤物件，報表套裝 ID 已作為函數中的必要引數存在。
