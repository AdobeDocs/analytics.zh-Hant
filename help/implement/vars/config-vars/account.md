---
title: account
description: 使用 account 變數決定要將資料傳送至哪個報表套裝。
feature: Variables
exl-id: 075d20be-6109-4024-84c4-1d048678d2bd
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 47%

---

# account

>[!IMPORTANT]
>
>此變數已淘汰。如果您的實施需要修改報表套裝目的地，請使用 [`s.sa()`](../functions/sa-method.md) 函數。

在舊版 Adobe Analytics 中，`account` 變數會決定您要將資料傳送至哪個報表套裝。必須有報表套裝 ID 才能將資料傳送至 Adobe Analytics。

* 如果您使用Web SDK，報表套裝位於Web SDK所傳送資料所在之資料流的Adobe Analytics服務設定中。
* 如果您使用Adobe Analytics擴充功能，報表套裝位於 [!UICONTROL 程式庫管理] 設定Adobe Analytics擴充功能時設定折疊式功能表。
* 如果您使用 [`s_gi()`](../functions/s-gi.md) 函式來實例化Analytics追蹤物件，報表套裝ID已作為函式中的必要引數存在。
