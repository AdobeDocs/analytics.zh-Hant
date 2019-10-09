---
description: 資料隱私權中用於許可管理的變數。
seo-description: 資料隱私權中用於許可管理的變數。
seo-title: 同意管理變數
solution: Analytics
title: 同意管理變數
topic: 管理工具
translation-type: tm+mt
source-git-commit: 492e9405c82183f6beb6588cd0dc039fe15350f7

---


# 同意管理變數

為了在管理隱私權資料方面提供額外協助，我們提供一組保留變數，可搭配特定上下文資料變數使用。
這些同意管理變數提供易於使用的框架，用於擷取每個分析點擊的同意狀態。

## 變數

* 同意管理選擇退出
   * 保留變數：清單Prop
   * 類型：逗號分隔字串
   * 包含:
      * `contextData.['cm.ssf']=1` 顯示為SSF
      * `contextData.['opt.dmp']=N` 顯示為DMP
      * `contextData.['opt.sell']=N` 顯示為SELL

* 同意管理選擇加入
   * 保留變數：清單Prop
   * 類型：逗號分隔字串
   * 包含:
      * `contextData.['opt.dmp']=Y` 顯示為DMP
      * `contextData.['opt.sell']=Y` 顯示為SELL

## 報告

「同意管理變數」可透過Analytics管理控制台中提供的新隱私權設定啟用。

每個報表套裝皆可設定為：
1. 在「報告與分析」中，按一下「管理&gt;報告套裝」。
1. Select the report suite(s) where you are collecting media data and click [!UICONTROL Edit Settings &gt; Privacy Management]

   ![](assets/rsm-privacy-select.png)

1. 按一下「啟 [!UICONTROL 用資料隱私權報表] 」按鈕。  請注意：在啟用這些變數後，將無法關閉。

   ![](assets/rsm-privacy-enable.png)

1. 啟用後，您會看到確認訊息。

   ![](assets/rsm-privacy-config.png)

1. 保留的變數現在可用於報告。  請參閱「同意管理選擇退出」和「同意管理選擇加入」。

   ![](assets/rsm-privacy-reports.png)

## 實施

已預先定義三個上下文資料變數，以搭配同意管理保留變數運作。  每位實施工程師都必須決定如何管理並保留這些變數的設定。

如需實 [作上下文資料變數的一般指引](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html) ，請參閱上下文資料變數。

### SSF

* 上下文資料: `contextData.['cm.ssf']`
* 接受的值：
   * `1` -傳送值時， `1`這表示「伺服器端轉送」處於退出狀態。 與此變 `1` 數配對的值會封鎖與Adobe Audience manager共用此點擊的情形。 請參 [閱AAM ePrivacy Compliance。](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)
   * 此參數不接受其他值

### DMP

* 上下文資料: `contextData.['opt.dmp']`
* 接受的值：
   * `N` -傳送值時， `N`這表示消費者選擇不共用至資料管理平台。 請注意，目前AAM不會共用區塊。  使用SSF進行此功能。
   * `Y` -傳送值時， `Y`這表示消費者選擇分享至資料管理平台。

### 銷售

* 上下文資料: `contextData.['opt.sell']`
* 接受的值：
   * `N` -傳送值時， `N`這表示消費者選擇不分享或銷售資料給第三方。
   * `Y` -傳送值時 `Y`，這表示消費者選擇分享或銷售資料給第三方。
