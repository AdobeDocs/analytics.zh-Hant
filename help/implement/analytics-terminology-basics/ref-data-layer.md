---
description: 「資料層」是 JavaScript 物件的架構，由開發人員將其插入頁面中。
keywords: Analytics Implementation;data layer;digitalData
title: 資料層
topic: Developer and implementation
uuid: dedb2a50-06f3-4354-8993-a25d4952ce1e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 資料層

_資料層_&#x200B;是 JavaScript 物件的架構，由開發人員將其插入頁面中。追蹤工具 (包括 Adobe Experience Platform Launch 和 Dynamic Tag Management 等標籤管理系統) 可使用資料層來填入報表。

在網站上實施資料層，可為您的實施提供最大的控制與彈性，且在未來階段只需進行最簡單的維護。這些 JavaScript 物件的名稱理論上是任意的，但最佳作法是使用一致且可預測的名稱。開發人員可能已經擁有資料層，或格式的偏好設定。追蹤社群已建立了一些不同的標準作為起點。[適用於 Analytics 實施的資料層](assets/datalayer-documentation.pdf)規格文件使用 W3C 標準「digitalData」物件，其為最多種追蹤技術所接受，以防需要將資料層用於此 DTM 實施以外的地方。
