---
title: 行動生命週期維度
description: 根據使用Mobile SDK所收集資料的Dimension。
feature: Dimensions
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 55%

---

# 行動生命週期維度

*此頁面會參考經常透過Adobe Experience Platform Mobile SDK追蹤的資料。 如需使用使用者代理程式的行動裝置資訊，請參閱 [行動查詢維度](mobile-dimensions.md). 如需使用行動SDK追蹤的量度，請參閱 [行動生命週期量度](../metrics/lifecycle-metrics.md).*

| 生命週期維度名稱 | 說明 | 內容資料變數 |
| --- | --- | --- |
| [!UICONTROL 首次發行日期] | | TBD （此為安裝日期嗎？） |
| [!UICONTROL 裝置名稱 (SDK)] | | `a.DeviceName` |
| [!UICONTROL 作業系統版本 (SDK)] | | `a.OSVersion` |
| [!UICONTROL 解析度(SDK)] | | `a.Resolution` |
| [!UICONTROL 贏取來源] | | `a.referrer.campaign.source` |
| [!UICONTROL 應用程式 ID] | | `a.AppID` |
| [!UICONTROL 贏取媒體] | | `a.referrer.campaign.medium` |
| [!UICONTROL 贏取詞彙] | | `a.referrer.campaign.term` |
| [!UICONTROL 贏取內容] | | `a.refferer.campaign.content` |
| [!UICONTROL 贏取名稱] | | `a.referrer.campaign.name` |
| [!UICONTROL 位置 (10 公里以內)] | | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL 位置 (100 公尺以內)] | | `a.loc.lat.b` + `a.loc.lon.b` |
| [!UICONTROL 位置 (1 公尺以內)] | | `a.loc.lat.c` + `a.loc.lon.c` |
| [!UICONTROL 興趣點名稱] | | `a.loc.poi` |
| [!UICONTROL 至興趣點中心的距離] | | `a.loc.dist` |
| [!UICONTROL 啟動次數] | | `a.Launches` |
| [!UICONTROL 首次使用後間隔天數] | | `a.DaysSinceFirstUse` |
| [!UICONTROL 動作名稱] | | 待定 |
| [!UICONTROL 期限值 (evar)] | | `a.ltv.amount` |
| [!UICONTROL 主要信標] | | 待定 |
| [!UICONTROL 次要信標] | | 待定 |
| [!UICONTROL UUID 信標] | | 待定 |
| [!UICONTROL 鄰近地區信標] | | 待定 |
| [!UICONTROL 上次使用後間隔天數] | | `a.DaysSinceFirstUse` |
| [!UICONTROL 小時 (SDK)] | | `a.HourOfDay` |
| [!UICONTROL 星期 (SDK)] | | `a.DayOfWeek` |
| [!UICONTROL 興趣點ID] | | 待定 |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
