---
title: 登入維度
description: 列出登入維度及其使用情形。
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 58%

---


# 登入維度

*此說明頁面說明登入作為維度時的運作方式。若要瞭解登入作為量度時的運作方式，請參閱[登入](../metrics/entries.md)量度。*

登入維度以造訪為基礎。他們會記錄第一個維度項目，並將其保存在該次瀏覽的整個期間。 報表套裝設定中的[流量變數](/help/admin/admin/c-traffic-variables/traffic-var.md)下方所有已啟用路徑分析的變數，都可使用登入維度。

## 將資料填入登入維度中

指定的登入維度以其相關聯的流量變數為基礎。如果非登入變數有資料，則其相關聯的登入維度也會包含資料。如果您的流量變數包含資料，即無須對登入維度進行實作變更。

## 維度項目

由於項目變數通常以實作中的自訂字串為基礎，因此您的組織會決定維度項目。 給定錄入維中的值與關聯的非錄入維中的維項匹配。 例如，「登入頁面」維度中的維度項目在「頁面」維度中包含類似的維度項目。

## 登入頁面原始

「登入頁面原始」維度的運作方式與其他登入維度不同。此維度不會保存指定造訪的登入頁面，而是會保存該訪客的 Cookie 在整個存留期內的第一個登入頁面。For example, if you land on `https://example.com/page4` for your first visit to the site, then a year later land on `https://example.com/store`, The &#39;Entry page original&#39; dimension lists `https://example.com/page4` as the dimension item.
