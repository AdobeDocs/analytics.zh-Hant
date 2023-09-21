---
title: 瀏覽器
description: 使用的瀏覽器名稱和版本。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 38%

---

# 瀏覽器

「[!UICONTROL 瀏覽器]『 [維度](overview.md) 報告傳送點選的瀏覽器名稱和版本。 此維度有助於瞭解訪客最常使用的瀏覽器。 測試新版網站時，您可以在此維度的前幾大瀏覽器上執行這些測試，以發揮最佳品質控制效果。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。

## 維度項目

維度項目包括使用的瀏覽器名稱和版本。相同瀏覽器的不同版本是分別的維度項目。

部分維度項目包含 `"(unknown version)"`，而不是版本號碼。此維度項目會參照 Adobe 尚未新增至其查閱表格的最新瀏覽器版本。由於瀏覽器經常更新，所以特定瀏覽器的 `"(unknown version)"` 為通用且暫時。Adobe 一般會在每月維護版本更新查閱表格。

## 標籤和定義的變更

以下是瀏覽器在報表中的呈現方式變更清單。 這些變更可能會影響您的報表或任何依賴這些值的邏輯，例如區段。

### 從瀏覽器中移除公司

從Chrome、Edge和Firefox瀏覽器的100版開始，公司名稱將不再出現在瀏覽器前。 如果使用者有以瀏覽器名稱為基礎的區段定義，這可能會影響使用者。 例如，從110版開始，包含「瀏覽器包含&quot;Google&quot;的定義」的區段將不再識別Chrome瀏覽器。

範例：

Chrome 109版將顯示為「Google Chrome 109」。
Chrome 110版將顯示為「Chrome 109」。

### 移除Chrome的行動和非行動裝置之間的區別

從Chrome 110開始，行動和非行動版本的Chrome將標示為相同。 目前，行動版本與非行動版本會個別加上標籤。 重要的是，這會變更名稱的含義，而非「行動」。 「Chrome 109」為非行動裝置（亦即案頭）「Chrome 110」為行動裝置且非行動裝置。 同樣地，如果您的瀏覽器名稱中有參照「行動」的區段定義，這些定義可能無法再正常運作。 您可以使用行動裝置細分和劃分，比較行動和非行動裝置流量。

範例：

Mobile Chrome 109會顯示為「Chrome Mobile 109」。
Non-Mobile Chrome 109會顯示為「Chrome 109」。

Mobile Chrome 110會顯示為「Chrome 110」。
非行動Chrome 110會顯示為「Chrome 110」。
