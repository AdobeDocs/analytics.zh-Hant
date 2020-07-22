---
title: 登入維度
description: 列出條目維度及其使用。
keywords: entry page, entry site section, entry server, entry custom insight
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---


# 登入維度

*此幫助頁說明條目如何作為維運作。 如需登入點如何當做度量的詳細資訊，請參閱「登[入點](../metrics/entries.md)」度量。*

登入維度是以瀏覽為基礎。 他們會記錄第一個維度項目，並將其保存在該次瀏覽的整個期間。 「報表套裝」設定中的「流量變數」下方啟用路徑分析的所 [有變數](/help/admin/admin/c-traffic-variables/traffic-var.md) ，都可使用項目維度。

## 以資料填入項目維度

指定的進入維度是以其關聯的流量變數為基礎。 如果非登入變數有資料，其關聯的登入維度也包含資料。 如果您的流量變數包含資料，則輸入維度不需要實施變更。

## 維度項目

由於項目變數通常以實作中的自訂字串為基礎，因此您的組織會決定維度項目。 給定錄入維中的值與關聯的非錄入維中的維項匹配。 例如，「登入頁面」維度中的維度項目在「頁面」維度中包含類似的維度項目。

## 登入頁面原始

「登入頁面原始」維度的運作方式與其他登入維度不同。 它不會保留特定瀏覽的登入頁面，而是會保留該訪客Cookie整個生命週期中的第一個登入頁面。 例如，如果您第一次 `https://example.com/page4` 瀏覽網站，一年後登入，「登入頁面原始」維度會列 `https://example.com/store``https://example.com/page4` 出為維度項目。
