---
title: account
description: （已淘汰）決定要將資料傳送到的報表套裝。
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 38%

---

# account

>[!IMPORTANT]
>
>此變數已淘汰。如果您的實施需要修改報表套裝目的地，請使用 [`s.sa()`](../functions/sa-method.md) 函數。

在舊版 Adobe Analytics 中，`account` 變數會決定您要將資料傳送至哪個報表套裝。必須有報表套裝 ID 才能將資料傳送至 Adobe Analytics。

* 如果您使用Web SDK，報表套裝位於Web SDK傳送資料的「資料流」內的Adobe Analytics服務設定中。
* 如果您使用Adobe Analytics擴充功能，設定Adobe Analytics擴充功能時，報表套裝位於[!UICONTROL 資料庫管理]摺疊式功能表底下。
* 如果您使用[`s_gi()`](../functions/s-gi.md)函式將Analytics追蹤物件例項化，則報表套裝ID已作為函式中的必要引數存在。
