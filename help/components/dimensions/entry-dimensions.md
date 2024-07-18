---
title: 登入維度
description: 列出登入維度及其使用情形。
keywords: 登入頁面, 登入網站區域, 登入伺服器, 登入客戶分析
feature: Dimensions
exl-id: 424e2a9a-05ac-4397-921b-c8d7567348ed
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 75%

---

# 進入維度

*此說明頁面說明登入作為[維度](overview.md)的運作方式。 若要瞭解登入作為量度時的運作方式，請參閱[登入](../metrics/entries.md)量度。*

登入維度以[造訪為基礎](../metrics/visits.md)。 這類維度會記錄第一個維度項目，並在該次造訪的整個期間加以持續保存。報表套裝設定中的[流量變數](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/c-traffic-variables/traffic-var.md)下方所有已啟用路徑分析的變數，都可使用登入維度。

>[!TIP]
>如果您想要根據造訪的首次點選而非造訪中看到的第一個值來檢視資料，可以使用[區段](/help/components/segmentation/seg-overview.md)。 使用[點選深度](hit-depth.md)等於1的點選容器，然後將該區段與所需變數搭配使用。

## 將資料填入登入維度中

指定的專案[維度](overview.md)是以其相關聯的流量變數為基礎。 如果非登入變數有資料，則其相關聯的登入維度也會包含資料。如果您的流量變數包含資料，即無須對登入維度進行實施作業變更。

## 維度項目

由於登入變數通常以您實施作業中的自訂字串為基礎，因此您的組織會決定維度項目。指定登入維度中的值會與其相關的非登入維度中的維度項目相符。例如，「登入頁面」維度中的維度項目，會與「頁面」維度中的維度項目相似。

## 登入頁面原始

「登入頁面原始」維度的運作方式與其他登入維度不同。此維度不會保存指定造訪的登入頁面，而是會保存該訪客的 Cookie 在整個存留期內的第一個登入頁面。例如，如果您在第一次造訪網站時進入了 `https://example.com/page4`，並在一年後進入 `https://example.com/store`，則「登入頁面原始」維度會將 `https://example.com/page4` 列為維度項目。
