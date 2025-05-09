---
description: 查閱表格以根據頁面事件判斷點選的型別。
keywords: 頁面；事件；頁面事件；post_page_event
title: 頁面事件查閱
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: e16b0d7b3fe585dc8e9274a77833ad5af3c63124
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 4%

---

# 頁面事件查閱

查閱表格以根據`page_event`值來判斷點選的型別。 如[資料欄參考](datafeeds-reference.md)中所述，`page_event`和`post_page_event`欄是無正負號的tinyint。

* 請參閱[`t()`](/help/implement/vars/functions/t-method.md)以瞭解如何實作AppMeasurement和Web SDK的頁面檢視呼叫。
* 請參閱[`tl()`](/help/implement/vars/functions/tl-method.md)以瞭解如何實作AppMeasurement和Web SDK的連結追蹤呼叫。
* 請參閱[使用Adobe Experience Platform Edge Network實作Adobe Analytics](/help/implement/aep-edge/overview.md)，瞭解Adobe Analytics如何將XDM裝載轉譯為頁面事件型別。

| `page_event` 值 | `post_page_event` 值 | 說明 |
| --- | --- | --- |
| `0` | `0` | 所有標準頁面檢視呼叫。 這是大多數點選的預設值。 |
| `10` | `100` | 自訂連結。 將連結型別設定為`o` (AppMeasurement)或`xdm.web.webInteraction.type`設定為`other` (網頁SDK或行動SDK)。 |
| `11` | `101` | 下載連結。 將連結型別設定為`d` (AppMeasurement)或`xdm.web.webInteraction.type`設定為`download` (網頁SDK或行動SDK)。 |
| `12` | `102` | 退出連結。 將連結型別設定為`e` (AppMeasurement)或`xdm.web.webInteraction.type`設定為`exit` (網頁SDK或行動SDK)。 |
| `31` | `76` | 媒體開始 |
| `32` | `77` | 媒體更新（無其他變數處理） |
| `33` | `78` | 媒體更新（使用其他變數處理） |
| `40` | `80` | 調查 |
| `50` | `50` | 串流媒體開始 |
| `51` | `51` | 串流媒體關閉 |
| `52` | `52` | 串流媒體拖曳 |
| `53` | `53` | 串流媒體持續運作 |
| `54` | `54` | 串流媒體廣告開始 |
| `55` | `55` | 串流媒體廣告關閉 |
| `56` | `56` | 串流媒體廣告拖曳 |
| `60` | `60` | Primetime媒體開始 |
| `61` | `61` | Primetime媒體關閉 |
| `62` | `62` | Primetime媒體清理 |
| `63` | `63` | Primetime媒體保持連線 |
| `64` | `64` | Primetime媒體廣告開始 |
| `65` | `65` | Primetime媒體廣告關閉 |
| `66` | `66` | Primetime媒體廣告拖曳 |
| `70` | `70` | 包含Target活動資料 |
