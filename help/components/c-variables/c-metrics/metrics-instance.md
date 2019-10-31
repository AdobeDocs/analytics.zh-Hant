---
description: 設定變數之值的次數。
keywords: 例項
seo-description: 設定變數之值的次數。
seo-title: 例項
solution: Analytics
title: 例項
topic: 量度
uuid: fec94bdd-a1dc-4cb0-8983-ea575b69589f
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 例項

設定變數之值的次數。

會針對所有點擊類型計算例項，但由於持續性而在隨後的點擊上記錄變數的值時，則不計算例項。

例如，如果使用者透過 [!DNL example.com] 來到您的網站，您網站上的第一個影像請求會包含 [!DNL example.com] 的反向連結。當設定此值時，即使該瀏覽期間檢視的所有頁面都已記錄此反向連結，仍會將一個例項歸因於 [!DNL example.com]。

在 2011 年年中引進 Data Warehouse 轉換變數的例項，可讓 Data Warehouse 請求將特定的轉換變數例項視為量度。這些度量不適用於引進日期前的報告。
