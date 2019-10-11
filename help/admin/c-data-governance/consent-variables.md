---
description: 資料隱私權中用於許可管理的變數。
seo-description: 資料隱私權中用於許可管理的變數。
seo-title: 同意管理變數
solution: Analytics
title: 同意管理變數
topic: 管理工具
translation-type: tm+mt
source-git-commit: a272be92292f3a12be19a5d6fd061b32a565448c

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

您可以透過Analytics管理控制台中提供的新隱私權設定，啟用「同意管理變數」。

每個報表套裝皆可設定如下：
1. In Reports &amp; Analytics click **[!UICONTROL Admin &gt; Report Suites.]**
1. Select the report suite(s) where you are collecting media data and click **[!UICONTROL Edit Settings &gt; Privacy Management.]**

   ![](assets/rsm-privacy-select.png)

1. 按一下「啟 **[!UICONTROL 用資料隱私權報表]** 」按鈕。 **** 注意：啟用後，這些變數就無法關閉。

   ![](assets/rsm-privacy-enable.png)

1. 啟用後，您會看到確認訊息。

   ![](assets/rsm-privacy-config.png)

1. 保留的變數現在可用於報告。  請參閱「同意管理選擇退出」和「同意管理選擇加入」。

   ![](assets/rsm-privacy-reports.png)

## 實施

已預先定義三個上下文資料變數，以搭配同意管理保留變數運作。  每位實施工程師都必須決定如何管理並保留這些變數的設定。

如需實 [作上下文資料變數的一般指引](https://docs.adobe.com/help/en/analytics/implementation/javascript-implementation/variables-analytics-reporting/context-data-variables.html) ，請參閱上下文資料變數。

### SSF

* 上下文資料：contextData.['cm.ssf']
* 接受的值：
   * 1 —— 傳送值"1"時，這表示伺服器端轉送處於選擇退出狀態。 值"1"與此變數搭配使用，將會封鎖此點擊與Adobe Audience manager的共用。 請參 [閱AAM ePrivacy Compliance。](https://docs.adobe.com/help/en/analytics/integration/audience-analytics/audience-analytics-workflow/ssf-gdpr.html)
   * 此參數不接受其他值。

### DMP

* 上下文資料：contextData.['opt.dmp']
* 接受的值：
   * N —— 傳送值"N"時，這表示消費者選擇不共用至資料管理平台。 **** 注意：將此變數設為"N"目前並不會封鎖AAM的共用，但是，AAM功能的封鎖呼叫將會在2020年初新增。 目前，Adobe建議同時設 `c.cm.ssf=1` 定 `c.opt.dmp=N` 和以封鎖點擊傳送至AAM。
   * Y —— 傳送值"Y"時，這表示消費者選擇分享至資料管理平台。

### 銷售

* 上下文資料：contextData.['opt.sell']
* 接受的值：
   * N —— 傳送值"N"時，這表示消費者選擇不分享或銷售資料給第三方。
   * Y —— 傳送值"Y"時，這表示消費者選擇分享或銷售資料給第三方。
