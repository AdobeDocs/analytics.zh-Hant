---
description: 查閱表格以根據 page_event 值來判斷點擊的類型。
keywords: Data Feed;page;event;page_event;post_page_event
title: 頁面事件查閱
topic: Reports and analytics
uuid: 73af597c-5560-466e-94b2-ddd1d64797c8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 頁面事件查閱

查閱表格以根據 page_event 值來判斷點擊的類型。

| 點擊類型 | `page_event` value | `post_page_event` value |
| --- | --- | --- |
| 頁面檢視 | 0:來自行動SDK的 `trackState` 所有頁面檢視呼叫和呼叫 | 與 `post_page_event` |
| 連結追蹤 | 10:行動SDK `trackAction` 的<br>11中的自訂連結和呼叫：下載連結<br>12:退出連結 | 100:行動SDK `trackAction` 的<br>101中的自訂連結和呼叫：下載連結<br>102:退出連結 |
| 里程碑視訊 | 31:媒體開始<br>32:媒體更新（無其他變數處理）<br>33:媒體更新（含其他變數） | 76:媒體開始<br>77:媒體更新（無其他變數處理）<br>78:媒體更新（含其他變數） |
| 心率視訊 | 50:媒體串流開始（非黃金時段）<br>51:媒體串流關閉（非黃金時段）<br>52:媒體串流清除（非黃金時段）<br>53:媒體串流保持活力（非黃金時段）<br>54:媒體串流廣告開始（非黃金時段）<br>55:媒體串流及關閉（非黃金時段）<br>56:媒體串流廣告清除（非黃金時段）<br>60:黃金時段媒體串流開始<br>61:黃金時段媒體串流關閉<br>62:黃金時段媒體串流清<br>理63:黃金時段媒體串流保持活<br>力64:黃金時段媒體串流廣告<br>65:黃金時段媒體串流及<br>66:Primetime媒體串流與清除 | 與 `post_page_event` |
| 調查 | 40:從「調查」產生的任何呼叫 | 80:從「調查」產生的任何呼叫 |
| 目標分析 | 70:點擊包含Target活動資料 | 與 `post_page_event` |
