---
title: 建立報表套裝
description: 在Adobe Analytics中建立資料收集的基本容器。
translation-type: tm+mt
source-git-commit: 6c57780d0ecf65669c1a5306dde267f6e48f1cc4

---


# 建立報表套裝

報表套裝是Adobe Analytics用來提取報表的資料孤島。 組織可以有許多報表套裝，每個報表套裝包含不同的資料集。 雖然個別報表套裝在過去很重要，但擁有單一報表套裝已變得更有利。 虛擬報表套裝和報表時間處理的引入，可讓使用者建立自己的資料子集，讓使用者靈活地取得全域和網站特定資料。

本文的設計對象為系統層級管理員或分析管理員，以準備資料收集。

## 必備條件

[Adobe Analytics第一份管理指南](first-admin-guide.md):確保系統層級管理員已授與您透過Experience Cloud Admin Console存取Adobe Analytics的權限

## 建立報表套裝

> [!NOTE] 此外，您也可以使用舊版管理員在Adobe Analytics中建立報表套裝。 Adobe建議使用此處概述的報表套裝設定精靈。

1. 使用您的 Adobe ID 憑證登入 [experiencecloud.adobe.com](https://experiencecloud.adobe.com)。
1. 按一下右上角 9 個方塊的圖示，然後按一下 Analytics 彩色標誌。
1. 您應會自動出現「歡迎使用Adobe Analytics」模式視窗。 如果您沒有，請按一下右上方的說明圖示，然後選取「歡迎使用Adobe Analytics」。
1. 在模態窗口中，按一下「開始設定」(Start Setup)。
1. 請依照每個提示進行，概述屬性類型、產業和時區等基本概念。 按一下「下一步」。
1. 報表套裝現在已建立。 Adobe也建議使用開發報表套裝，因此測試不會污染客戶資料。 按一下右上方的說明圖示，然後再次選取「歡迎使用Adobe Analytics」。
1. 在模態窗口中，按一下「開始設定」(Start Setup)。
將此報表套裝命名為相同，但在結尾附加"- DEV"。 由於此報表套裝只會接收內部流量，因此估計的大小可以是最小的。
1. 按一下「下一步」以完成您的開發報表套裝的建立。

## 疑難排解

**登入Experience cloud後，Analytics圖示會變灰。**

這表示您的帳戶尚未獲得Analytics的正確權限。 與組織中的系統層級管理員合作，以確保您屬於具備存取Adobe Analytics之適當權限的設定檔。

**登入Adobe Analytics後，會遺失「歡迎使用Adobe Analytics」彈出式和下拉式清單。**

請確定您已透過Experience cloud登入，而非透過my.omniture.com登入。 透過my.omniture.com登入的使用者沒有可用的報表套裝設定精靈。

## 下一步

[在Launch中建立並設定Adobe Analytics的屬性](/help/implement/implement-with-launch/create-analytics-property.md):建立區域以管理您的Analytics實作
