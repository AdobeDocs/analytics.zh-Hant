---
description: 查閱表格以根據 page_event 值來判斷點擊的類型。
keywords: 資料摘要;頁面;活動;頁面活動;公佈頁面活動
title: 頁面事件查閱
feature: Data Feeds
exl-id: ef0467df-b94b-4cec-b312-96d8f42c23b0
source-git-commit: 4daa5c8bdbcb483f23a3b8f75dde9eeb48516db8
workflow-type: ht
source-wordcount: '231'
ht-degree: 100%

---

# 頁面事件查閱

查閱表格以根據 page_event 值來判斷點擊的類型。

| 點擊類型 | `page_event` 值 | `post_page_event` 值 |
| --- | --- | --- |
| 頁面檢視 | 0：來自行動 SDK 的所有頁面檢視呼叫和 `trackState` 呼叫 | 與 `page_event` 的值相同 |
| 連結追蹤 | 10：行動 SDK 的自訂連結和 `trackAction` 呼叫<br>11：下載連結<br>12：退出連結 | 100：行動 SDK 的自訂連結和 `trackAction` 呼叫<br>101：下載連結<br>102：退出連結 |
| 里程碑影片 | 31：媒體開始<br>32：媒體更新 (無其他變數處理)<br>33：媒體更新 (含其他變數) | 76：媒體開始<br>77：媒體更新 (無其他變數處理)<br>78：媒體更新 (含其他變數) |
| 心率視訊 | 50：媒體串流開始 (非 Primetime)<br>51：媒體串流關閉 (非 Primetime)<br>52：媒體串流清除 (非 Primetime) <br>53：媒體串流保持運作 (非 Primetime)<br>54：媒體串流廣告開始 (非 Primetime)<br>55：媒體串流廣告關閉 (非 Primetime)<br>56：媒體串流廣告清除 (非 Primetime)<br>60： Primetime 媒體串流開始<br>61：Primetime 媒體串流關閉<br>62：Primetime 媒體串流清除<br>63：Primetime 媒體串流保持運作<br>64：Primetime 媒體串流廣告開始<br>65：Primetime 媒體串流廣告關閉<br>66：Primetime 媒體串流廣告清除 | 與 `page_event` 的值相同 |
| 調查 | 40：從「調查」產生的所有呼叫 | 80：從「調查」產生的所有呼叫 |
| 目標分析 | 70：點擊包含 Target 活動資料 | 與 `page_event` 的值相同 |
