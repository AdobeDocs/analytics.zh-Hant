---
title: s_objectID
description: 協助 Activity Map 辨識網站上的獨特連結。
translation-type: ht
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# s_objectID

`s_objectID` 變數提供連結的唯一識別碼。它可用來讓 [Activity Map](/help/analyze/activity-map/activity-map.md) 中的報表更準確。如果您的頁面上有經常變更的連結，可以使用 `s_objectID` 變數來告知 Activity Map 留意唯一連結位置，讓它能夠正常地將資料正確分組。

如果 Activity Map 的正確性對貴組織至關重要，Adobe 建議您在網站上於連結的 `onClick` 事件中加入 `s_objectID` 變數。如需詳細資訊，請參閱「Analyze 使用指南」中的 [Activity Map 連結追蹤使用案例](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md)。

## Adobe Experience Platform Launch 中的物件 ID

Launch 中沒有使用此變數的專用欄位。依照 AppMeasurement 語法，使用自訂程式碼編輯器。

## AppMeasurement 和 Launch 自訂程式碼編輯器中的 s_objectID

`s_objectID` 變數是全域變數，表示它能獨立於 Analytics 追蹤物件 (預設為 `s`) 之外運作。此變數的有效值可以是任何字串，長度最多 100 個位元組。如果此變數未定義，Activity Map 會將連結 URL 當做連結的識別碼。

此變數通常設定在 HTML 連結的 `onClick` 事件中。

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

> [!NOTE] 請一律加上 JavaScript 陳述式結尾的分號。Activity Map 必須有分號才能運作。

## 使用案例

每當您想要提高 Activity Map 報表的正確性時，`s_objectID` 變數就能派上用場。

### 從高度動態內容彙總連結

有些網站具有高度動態內容，如新聞網站或經常輪流展示商品的零售網站。由於 Activity Map 預設會將連結 URL 當做為識別碼，因此在連結經常變更的頁面上，它將難以理解點按數最多的區域。如果您在這些連結中使用 `s_objectID`，不論連結指向的 URL 為何，Activity Map 都能知道哪些連結可以彙總。

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

無論連結指向何處或變更的頻率為何，Activity Map 都能根據 `s_objectID` 中的值彙總資料。

### 將連結保留在頁面上

有些網站的連結雖然位在不同的地方，不過都指向同一個位置。例如，網站頁首和頁尾中的首頁連結。由於這些連結的 URL 都一樣，Activity Map 便會彙總其資料。您可以使用 `s_objectID` 變數來分隔:

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

即使連結指向相同的 URL，Activity Map 依然可以使用 `s_objectID` 變數在報表中正確區分。
