---
title: 行動生命週期維度
description: 根據使用Mobile SDK所收集資料的Dimension。
feature: Dimensions
exl-id: b7ba45d7-7d30-48a3-a747-ea9fbb253abb
source-git-commit: 4c472d9a99f15ed253b68124aa31bdc88554d9a5
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 26%

---

# 行動生命週期維度

*此頁面會參考經常透過Adobe Experience Platform Mobile SDK追蹤的資料。 如需使用使用者代理程式的行動裝置資訊，請參閱 [行動查詢維度](mobile-dimensions.md). 如需使用行動SDK追蹤的量度，請參閱 [行動生命週期量度](../metrics/lifecycle-metrics.md).*

| 生命週期維度名稱 | 說明 | 上下文資料變數 |
| --- | --- | --- |
| [!UICONTROL 首次啟動日期] | | 待定 |
| [!UICONTROL 裝置名稱(SDK)] | | `a.DeviceName` |
| [!UICONTROL 作業系統版本(SDK)] | | `a.OSVersion` |
| [!UICONTROL 解析度(SDK)] | | `a.Resolution` |
| [!UICONTROL 贏取來源] | | `a.referrer.campaign.source` |
| [!UICONTROL 應用程式ID] | | `a.AppID` |
| [!UICONTROL 贏取媒體] | | `a.referrer.campaign.medium` |
| [!UICONTROL 贏取詞語] | | `a.referrer.campaign.term` |
| [!UICONTROL 贏取內容] | | `a.refferer.campaign.content` |
| [!UICONTROL 贏取名稱] | | `a.referrer.campaign.name` |
| [!UICONTROL 位置 (10 公里以內)] | 訪客的經緯度，精確到小數點後的第一位。 例如， `040.9` `-111.9`. | `a.loc.lat.a` + `a.loc.lon.a` |
| [!UICONTROL 位置 (100 公尺以內)] | 訪客的經緯度，精確至小數點後的第三位。 例如， `040.932` `-111.931`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lon.a` + `a.loc.lon.b` |
| [!UICONTROL 位置 (1 公尺以內)] | 訪客的經緯度，精確到小數點後的第五位。 例如， `040.93231` `-111.93152`. | `a.loc.lat.a` + `a.loc.lat.b` + `a.loc.lat.c` + `a.loc.lon.a` + `a.loc.lon.b` + `a.loc.lon.c` |
| [!UICONTROL 興趣點名稱] | | `a.loc.poi` |
| [!UICONTROL 至興趣點中心的距離] | | `a.loc.dist` |
| [!UICONTROL 啟動次數] | | `a.Launches` |
| [!UICONTROL 首次使用後間隔天數] | | `a.DaysSinceFirstUse` |
| [!UICONTROL 動作名稱] | | 待定 |
| [!UICONTROL 期限值(evar)] | | `a.ltv.amount` |
| [!UICONTROL 信標Major] | | 待定 |
| [!UICONTROL 次要信標] | | 待定 |
| [!UICONTROL 信標UUID] | | 待定 |
| [!UICONTROL 鄰近地區指標] | | 待定 |
| [!UICONTROL 上次使用後間隔天數] | | `a.DaysSinceFirstUse` |
| [!UICONTROL 小時(SDK)] | | `a.HourOfDay` |
| [!UICONTROL 星期(SDK)] | | `a.DayOfWeek` |
| [!UICONTROL 興趣點ID] | | 待定 |

{style="table-layout:auto"}

<!-- Missing: Install Date -->
