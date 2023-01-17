---
title: 瀏覽器
description: 使用的瀏覽器名稱和版本。
feature: Dimensions
exl-id: 2bdf2a5a-3482-43fa-b2e1-fbea892918fb
source-git-commit: 39f1ac66fb6374c62f790f9a38a52fba3bf9bda1
workflow-type: tm+mt
source-wordcount: '397'
ht-degree: 38%

---

# 瀏覽器

「[!UICONTROL 瀏覽器]「 」維度會報告傳送點擊的瀏覽器名稱和版本。 此維度有助於了解訪客最常使用的瀏覽器。 測試新版網站時，您可以在此維度的前幾大瀏覽器上執行這些測試，以發揮最佳品質控制效果。

## 將資料填入此維度中

此維度會參考 Adobe 內部的查閱表格。查閱值以影像要求中 `User-Agent` 的 HTTP 標題為基礎。如果您使用 AppMeasurement 資料庫 (例如，透過 Adobe Experience Platform 中的標記)，此維度將可立即運作。

## 維度項目

維度項目包括使用的瀏覽器名稱和版本。相同瀏覽器的不同版本是分別的維度項目。

部分維度項目包含 `"(unknown version)"`，而不是版本號碼。此維度項目會參照 Adobe 尚未新增至其查閱表格的最新瀏覽器版本。由於瀏覽器經常更新，所以特定瀏覽器的 `"(unknown version)"` 為通用且暫時。Adobe 一般會在每月維護版本更新查閱表格。

## 標籤和定義的變更

以下為報表中呈現瀏覽器方式的變更清單。 這些變更可能會影響您的報表或任何依賴這些值的邏輯（例如區段）。

### 從瀏覽器移除公司

從Chrome、Edge和Firefox瀏覽器的100版開始，瀏覽器之前將不再顯示公司名稱。 如果使用者的區段定義是根據瀏覽器名稱而定，則這可能會影響使用者。 例如，包含「瀏覽器包含Google」定義的區段，從110版開始將不再識別Chrome瀏覽器。

範例：

Chrome 109版將顯示為「Google Chrome 109」。
Chrome 110版將顯示為「Chrome 109」。

### 移除Chrome專用行動與非行動裝置的區別

從Chrome 110開始，行動版和非行動版的Chrome都會被標示為相同。 目前，行動版和非行動版本會分別加上標籤。 重要的是，這會改變名稱的含義，而不使用「行動」。 「Chrome 109」為非行動裝置（亦即案頭版）「Chrome 110」為行動裝置和非行動裝置。 同樣地，如果您的瀏覽器名稱中有參考「行動」的區段定義，這些定義可能無法如預期運作。 您可以使用行動裝置分段和劃分來比較行動與非行動流量。

範例：

Mobile Chrome 109將顯示為「Chrome Mobile 109」。
非行動版Chrome 109將顯示為「Chrome 109」。

行動Chrome 110將顯示為「Chrome 110」。
非行動版Chrome 110會顯示為「Chrome 110」。
