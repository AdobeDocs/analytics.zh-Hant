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

# 帳戶

>[!IMPORTANT]
>
>此變數已淘汰。如果您的實施需要修改報表套裝目的地，請使用 [`s.sa()`](../functions/sa-method.md) 函數。

在舊版 Adobe Analytics 中，`account` 變數會決定您要將資料傳送至哪個報表套裝。必須有報表套裝 ID 才能將資料傳送至 Adobe Analytics。

* 如果使用Web SDK，則報告套件位於Web SDK向其發送資料的Datastream中的Adobe Analytics服務設定中。
* 如果使用Adobe Analytics分機，則報告套件位於 [!UICONTROL 庫管理] 配置Adobe Analytics分機時的手風琴。
* 如果使用 [`s_gi()`](../functions/s-gi.md) 函式以實例化Analytics跟蹤對象，該函式中已存在作為必需參數的報表套件ID。
