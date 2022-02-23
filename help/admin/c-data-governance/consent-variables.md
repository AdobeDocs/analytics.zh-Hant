---
description: 資料隱私權中的隱私權報表變數。
title: 隱私權報表變數
feature: Privacy
exl-id: 3f7980a4-d826-4554-a9a0-673fd5b79653
source-git-commit: f6199620033af9c8e304bd0f537d4e0b052ed64d
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 100%

---

# 隱私權報表變數

為了在管理隱私權資料方面提供額外協助，我們提供一組保留變數，可搭配特定上下文資料變數使用。
這些隱私權報表變數提供簡單易用的架構，可用來擷取每個 Analytics 點擊的隱私權狀態。

## 變數

* 同意管理選擇退出
   * 保留變數：清單 Prop
   * 類型：逗號分隔字串
   * 包含：
      * `contextData.['cm.ssf']=1` 顯示為 SSF
      * `contextData.['opt.dmp']=N` 顯示為 DMP
      * `contextData.['opt.sell']=N` 顯示為 SELL

* 同意管理選擇加入
   * 保留變數：清單 Prop
   * 類型：逗號分隔字串
   * 包含：
      * `contextData.['opt.dmp']=Y` 顯示為 DMP
      * `contextData.['opt.sell']=Y` 顯示為 SELL

## 報表

您可透過 Analytics Admin Console 中提供的新「隱私權」設定來啟用隱私權報表變數。

每個報表套裝皆可依照以下步驟設定：
1. 在 Reports &amp; Analytics 中，按一下&#x200B;**[!UICONTROL 「管理員 > 報表套裝」]**。
1. 選取您要收集媒體資料的報表套裝，然後按一下&#x200B;**[!UICONTROL 「編輯設定 > 隱私權管理」]**。

   ![](assets/rsm-privacy-select.png)

1. 按一下&#x200B;**[!UICONTROL 「啟用資料隱私權報表」]**&#x200B;按鈕。

   >[!NOTE]
   >
   > 這些變數一經啟用即無法關閉。

   ![](assets/rsm-privacy-enable.png)

1. 啟用後會顯示一則確認訊息。

   ![](assets/rsm-privacy-config.png)

1. Reports &amp; Analytics 和 Workspace 現在會提供保留的變數，以便分析。請參閱「同意管理選擇退出」和「同意管理選擇加入」。

   ![](assets/consent-management.png)

## 實作

已預先定義三個上下文資料變數，用於搭配隱私權報表管理保留變數使用。如何管理並保留這些變數的設定取決於每位實作工程師。

如需實作上下文資料變數的通用指引，請參閱[上下文資料變數](/help/implement/vars/page-vars/contextdata.md)。

### SSF

* 上下文資料：`contextData.['cm.ssf']`
* 接受的值：
   * 1 - 傳送「1」值時，表示伺服器端轉送處於選擇退出狀態。值「1」與此變數搭配使用，將會封鎖此點擊與 Adobe Audience Manager 間的共用。請參閱[ AAM ePrivacy 合規性](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/data-privacy.html?lang=en)。
   * 0 - 選用。對於同意目標行銷的客戶，請使用「0」值。未設定變數也會產生相同的結果。

### DMP

* 上下文資料：`contextData.['opt.dmp']`
* 接受的值：
   * N - 傳送「N」值時，表示消費者選擇不分享至資料管理平台。**注意**：自 2020 年 1 月 15 日起，將此變數設為「N」會封鎖伺服器端對 AAM 共用此點擊的操作。
   * Y - 傳送「Y」值時，表示消費者選擇分享至資料管理平台。

### SELL

* 上下文資料：`contextData.['opt.sell']`
* 接受的值：
   * N - 傳送「N」值時，表示消費者選擇不分享或銷售資料給第三方。
   * Y - 傳送「Y」值時，表示消費者選擇分享或銷售資料給第三方。
