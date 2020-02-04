---
title: s_objectID
description: 說明Activity map可識別您網站上的獨特連結。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# s_objectID

變 `s_objectID` 數提供連結的唯一識別碼。 它可用來讓 [Activity Map中的報表更](/help/analyze/activity-map/activity-map.md) 準確。 如果您的頁面上有經常變更的連結，則可使用變數來告知Activity map有唯一的連結位置，以便 `s_objectID` Activity map能夠視需要正確分組資料。

如果Activity map的正確性對您的組織至關重要，Adobe建議在您的 `s_objectID` 網站上發生連 `onClick` 結時加入變數。 如需詳 [細資訊，請參閱「分析使用指南](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) 」中的「Activity map連結追蹤使用案例」。

## Adobe Experience Platform Launch中的物件ID

Launch中沒有專用欄位可使用此變數。 依照AppMeasurement語法，使用自訂程式碼編輯器。

## AppMeasurement和Launch自訂代碼編輯器中的s_objectID

變 `s_objectID` 數是全域變數，表示它獨立於Analytics追蹤物件運作(依預`s` 設)。 此變數的有效值可以是長度高達100位元組的任何字串。 如果未定義此變數，Activity map會使用連結URL作為連結的識別碼。

此變數通常在HTML連結 `onClick` 的事件中設定。

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

> [!NOTE] 請一律包含結束JavaScript陳述式的分號。 Activity map必須有分號才能運作。

## 使用個案

只要 `s_objectID` 您想要提高Activity map報表的正確性，此變數就很有用。

### 從高動態內容匯總連結

有些網站具有高度動態的內容，例如新聞網站或經常旋轉項目的零售網站。 由於Activity map預設會使用連結URL做為識別碼，因此很難瞭解連結經常變更之頁面上點按最多的區域。 如果您使用這些 `s_objectID` 連結，Activity map會瞭解哪些連結可以匯總，不論其指向的URL為何。

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

無論連結指向何處或您變更這些連結的頻率為何，Activity map都會根據中的值匯整資料 `s_objectID`。

### 將連結保留在頁面上

有些網站的連結會指向不同位置的相同位置。 例如，您網站頁首和頁尾中的首頁連結。 由於這些連結具有相同的URL,Activity map會匯總其資料。 您可以使用變數來分 `s_objectID` 隔：

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

即使連結指向相同的URL,Activity map仍可使用變 `s_objectID` 數在報表中正確區分它們。
