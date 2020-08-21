---
title: account
description: 使用 account 變數決定要將資料傳送至哪個報表套裝。
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '109'
ht-degree: 100%

---


# account

>[!IMPORTANT]
>
>此變數已淘汰。如果您的實施需要修改報表套裝目的地，請使用 [`s.sa()`](../functions/sa-method.md) 函數。

在舊版 Adobe Analytics 中，`account` 變數會決定您要將資料傳送至哪個報表套裝。必須有報表套裝 ID 才能將資料傳送至 Adobe Analytics。

* 如果您使用 Adobe Experience Platform Launch，設定 Adobe Analytics 擴充功能時，報表套裝位於[!UICONTROL 程式庫管理]摺疊式功能表底下。
* 如果您使用 [`s_gi()`](../functions/s-gi.md) 函數來實例化 Analytics 追蹤物件，報表套裝 ID 已作為函數中的必要引數存在。
