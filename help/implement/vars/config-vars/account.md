---
title: account
description: 使用 account 變數決定要將資料傳送至哪個報表套裝。
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: ht
source-wordcount: '110'
ht-degree: 100%

---

# account

>[!IMPORTANT]
>
>此變數已淘汰。如果您的實施需要修改報表套裝目的地，請使用 [`s.sa()`](../functions/sa-method.md) 函數。

在舊版 Adobe Analytics 中，`account` 變數會決定您要將資料傳送至哪個報表套裝。必須有報表套裝 ID 才能將資料傳送至 Adobe Analytics。

* 如果您使用 Adobe Experience Platform 中的標記，則在設定 Adobe Analytics 擴充功能時，報表套裝會位在「[!UICONTROL 資料庫管理]」摺疊式功能表底下。
* 如果您使用 [`s_gi()`](../functions/s-gi.md) 函數將 Analytics 追蹤物件實體化，則報表套裝 ID 會當做函數中的必要引數存在。
