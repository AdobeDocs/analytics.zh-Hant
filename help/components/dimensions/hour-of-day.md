---
title: 小時
description: 一天中的數值小時，不論哪一天。
feature: Dimensions
exl-id: b9361534-7e58-41ed-9a38-c02aeed7a2d8
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 95%

---

# 小時

「小時」[維度](overview.md)會將任何指定日的數值小時報告為維度專案。 例如，如果您的報表橫跨 1 月 1 日至 1 月 7 日，則每天的第 1 個小時都會分組到相同的維度項目中。如果您想要依當天相對時間劃分報表，但不要以靜態小時作為維度項目，此報表十分實用。在排程報表中，當此維度跟著所選日期範圍變動時特別有用。

此維度是以報表套裝的時區為依據，而非訪客的當地時區。例如，若您的報表套裝使用美國山區時間，而加州的訪客在太平洋時間上午 10:00 造訪您的網站，則點擊群組會在維度項目 `11:00 AM` 底下。如果您想使用會記錄本機訪客時間的維度，Adobe 建議使用 [getTimeParting](/help/implement/vars/plugins/gettimeparting.md) 外掛程式。

## 將資料填入此維度中

此維度可直接用於所有實施作業。如果報告套裝包含資料，此維度即會運作。

## 維度項目

維度項目包括 `12:00 AM` - `11:00 PM`，代表發生點擊的當天某小時 (無條件捨去)。例如，如果點擊是在下午 3:58 產生，則會分組在維度項目 `3:00 PM` 下。

## 日光節約時間

日光節約時間慣例是在春季將時鐘往前設定一小時，並在秋季將時鐘往後設定一小時。如果報表套裝的時區使用 DST，Adobe 會相應調整該小時的資料。

* **日光節約時間開始時**：三月時，報表通常會在日光節約時間開始的資料中顯示一個小時間隔。該小時不存在，因此它不屬於資料收集的一部分。請注意，少量資料仍可能歸入這個小時中。Adobe 資料收集伺服器需花幾秒鐘時間 (最多一分鐘) 才能將 DST 調整納入考量。
* **日光節約時間結束時**：十一月時，報表通常會在日光節約時間結束時顯示雙重堆疊小時。該小時發生了兩次，因此兩個小時都會在報表中彙總。
