---
title: 建立報表套裝
seo-title: 在Adobe Analytics中建立報表套裝
description: 建立Adobe Analytics中資料收集的基本容器。
seo-description: 建立Adobe Analytics中資料收集的基本容器。
translation-type: tm+mt
source-git-commit: d195fb85711f58383577bf1d7b4da4078b909427

---


# 建立報表套裝

報表套裝是Adobe Analytics用來提取報表的資料孤島。組織可以有許多報表套裝，每個報表套裝都包含不同的資料集。雖然單獨報告套裝在過去很重要，但具有單一報表套裝變得更有利。虛擬報表套裝和報告時間處理的簡介可讓使用者建立自己的資料子集，允許靈活取得全域和網站專用資料。

本文是專為系統層級管理員或分析管理員所設計，用於準備資料收集。

## 必備條件

[Adobe Analytics第一個管理指南](first-admin-guide.md)：確保系統層級管理員已授與您透過Experience Cloud Admin Console存取Adobe Analytics的權限

## 建立報表套裝

> [!NOTE]注意：您也可以使用舊版管理員在Adobe Analytics中建立報表套裝。Adobe建議您使用此處概述的報表套裝設定精靈。

1. Log in to [experiencecloud.adobe.com](https://experiencecloud.adobe.com) using your Adobe ID credentials.
1. 按一下右上方的方形圖示，然後按一下彩色的Analytics標誌。
1. 您應該會看到「歡迎使用Adobe Analytics」模式視窗自動彈出。如果您沒有，請按一下右上方的說明圖示，然後選取「歡迎使用Adobe Analytics」。
1. 在模型視窗中，按一下「開始設定」。
1. 依照每個提示，概述基本的屬性類型、產業和時區。按一下「下一步」。
1. 現在會建立報表套裝。Adobe建議您也有開發報表套裝，因此測試不會影響客戶資料。按一下右上方的說明圖示，然後再次選取「歡迎使用Adobe Analytics」。
1. 在模型視窗中按一下「開始設定」。
請將此報表套裝命名為相同，但最後附加「-DEV」。由於此報表套裝只會接收內部流量，所以估計的大小可能是最小的。
1. 按一下「下一步」以完成開發報表套裝。

## 疑難排解

**登入Experience Cloud後，Analytics圖示會反灰。**

這表示您的帳戶尚未獲得Analytics的正確權限。在組織中使用系統層級管理員，確保您屬於具有存取Adobe Analytics權限的個人檔案。

**登入Adobe Analytics後，「歡迎使用Adobe Analytics」彈出式清單和下拉式清單遺失。**

確定您已透過Experience Cloud登入，而不是透過我的. omniture. com登入。透過my.omniture.com登入的使用者無法使用報表套裝設定精靈。

## 下一步

[在Launch中建立及設定Adobe Analytics的屬性](../../implement/implement-with-launch/create-analytics-property.md)：建立區域以管理您的Analytics實作
