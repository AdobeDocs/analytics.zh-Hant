---
description: Adobe Analytics 提供彈性的報告介面，供您產生多種複雜的報告。大部分報告都能迅速產生，但您仍可能遇到報告逾時或無法成功產生的問題。為了協助避免報告無法產生，本區段說明會影響報告產生速度的眾多因素。了解這些資訊有助於建構能夠成功產生的報告。
keywords: best practices;failure;timeout;troubleshooting;slow
title: 報告最佳實務與疑難排解
topic: Reports
uuid: d4eef0a3-1d26-4460-8a2b-962001c9f846
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 報告最佳實務與疑難排解

Adobe Analytics 提供彈性的報告介面，供您產生多種複雜的報告。大部分報告都能迅速產生，但您仍可能遇到報告逾時或無法成功產生的問題。為了協助避免報告無法產生，本區段說明會影響報告產生速度的眾多因素。了解這些資訊有助於建構能夠成功產生的報告。

>[!Note]
>這些建議適用於 Reports &amp; Analytics、Ad Hoc Analysis 以及 Report Builder，
>但不適用於 Analysis Workspace，Analysis Workspace 有其專屬的一套[最佳實務](/help/analyze/analysis-workspace/optimizing-performance.md)。這些建議也不適用於 Data Warehouse [最佳實務](https://marketing.adobe.com/resources/help/zh_TW/reference/data_warehouse_bp.html)。此外，
>[Adobe Analytics Reporting API 有另一套最佳實務](https://marketing.adobe.com/developer/en_US/get-started/best-practices/c-best-practices)可使用。

## 報告逾時和請求佇列 {#section_A42AD7E487C749B7B879BAFA814FFEF9}

**逾時**

單一報告劃分為多個請求 (每個劃分各一個請求)，而每個請求都有個別的逾時規範。排程報告所授與的逾時期限比在使用者介面中直接產生的報告長，也比較可能成功。

**報表套裝佇列**

每個報表套裝會維護個別的請求佇列。如果同時請求多個報告 (即使來自不同使用者)，同一時間只會產生少數報告。這些報告完成後，再依收到順序產生其餘報告。因此，如果報表套裝佇列中已有大量複雜的報告，原本可以迅速產生的報告有可能逾時。

## 影響報告速度的因素{#section_6BA937EB6CEC4CBCB71FAAD32F031DC2}

下列因素會拉長報告產生時間。增加這些因素其中之一也許不會造成該報告逾時，但會延遲報表套裝佇列中的其他報告，並造成後續報告逾時。

**報告時間範圍**

影響報告產生時間最大的因素是請求的月數。將月數從 3 降至 1 可以大幅減少產生時間，但將時間範圍從 1 個月降至 1 星期對報告產生時間並沒有太大影響。

**量度數**

隨著量度數增加，報告執行時間也會增加。移除量度通常可以改進報告產生時間。

**劃分數**

在報告內，每個劃分各代表一個請求。個別請求可以迅速完成，但在單一報告中執行數千個劃分，可能大幅減慢報告產生時間，並影響報表套裝佇列。

**區段複雜性**

考慮許多維度或有多個 (24+) 規則的區段，會提高處理影響程度並增加報告產生時間。

**唯一值數**

包含數十萬個唯一值的報告的產生速度會比包含較少唯一值的報告來得慢，即使使用區段或篩選器來減少最後出現在報告中的值數目也一樣。例如，顯示搜尋詞的報告產生速度通常比其他報告更慢，即使套用篩選器以只顯示包含特定值的搜尋詞也一樣。

## 其他報告選項{#section_FEF85C7FC6E14755A6086AFFF36E0EB4}

除了降低報告中的時間範圍、量度數和劃分數以外，下列指引有助於提高報告傳送的可靠性：

* 使用 Data Warehouse 來請求包含許多劃分或量度的報表。Data Warehouse 旨在產生這些報表類型。
* 將報告排程在非尖峰時間執行。如此可提高報告傳回的機率，因為報表套裝的請求佇列在這種時段更可能是空的。
* 您可使用 Report Builder 將報表劃分為較小的時間範圍以及包含較少量度的請求。接著可使用原生 Excel 功能，將各種請求的資料合併為單一報告。

