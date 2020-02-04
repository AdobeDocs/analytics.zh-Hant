---
title: 舊版 Adobe Experience Cloud Debugger
description: 安裝舊版 Adobe Experience Cloud Debugger。此除錯程式會檢查 Analytics、Target、Advertising Cloud、Identity Service、DTM 和 Launch 的標籤。
translation-type: tm+mt
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651

---


# 舊版 Adobe Experience Cloud Debugger

> [!IMPORTANT] 這個除錯工具已不再更新。Adobe 建議改用 [Adobe Experience Cloud Debugger Chrome 擴充功能](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)。

[!UICONTROL 舊版 Debugger] 會檢查大部分 Adobe Experience Cloud 服務的標籤。使用除錯程式，可讓您查看網站上任何指定頁面傳送到 Adobe 的資料。運用這類資訊，您就能針對組織的實作項目進行疑難排解或驗證。

## 安裝舊版 Debugger

建立 JavaScript 書籤小程式來安裝除錯程式。

### 步驟 1: 複製書籤小程式的程式碼

將以下代碼複製到您的剪貼簿:

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### 步驟 2: 將書籤小程式的程式碼貼入書籤

每個瀏覽器處理書籤的方式各異，但概念皆相同。書籤會以所需名稱建立，並將書籤小程式的程式碼設為 URL。

#### Chrome

如果您堅持不使用 [Chrome 擴充功能](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)，則可改用舊版除錯程式書籤小工具。

1. 按一下右上方的三點圖示，然後前往書籤 > 書籤管理員。您也可以按下 `Ctrl` + `Shift` + `O` (Windows) 或 `Cmd` + `Shift` + `O` (Mac)。
2. 在書籤管理員的右上方，按一下三點圖示，然後按一下「新增書籤」。
3. 在名稱欄位中，將其標示為「Adobe Experience Cloud Debugger」，然後將程式碼片段貼入 URL 欄位。
4. 使用書籤管理員將新的書籤小程式置於所需位置。

#### Firefox

1. 按一下右上方的三行圖示，然後前往資料庫 > 書籤 > 顯示所有書籤。您也可以按下 `Ctrl` + `Shift` + `B` (Windows) 或 `Cmd` + `Shift` + `B` (Mac)。
2. 按一下整理 > 新書籤。
3. 在名稱欄位中標示「Adobe Experience Cloud Debugger」，然後將程式碼片段貼入位置欄位。標籤和關鍵字欄位不是必填欄位。
4. 使用資料庫視窗將新的書籤小程式置於所需位置。

#### Edge

Edge無法手動建立書籤小程式，但書籤URL可以編輯成書籤小程式。

1. 按一下 URL 欄位右側的星形圖示，將目前頁面加入書籤。
2. 將書籤命名為「Adobe Experience Cloud Debugger」，並儲存在所需位置。
3. 按一下附帶線條的星形圖示，開啟我的最愛列。
4. 以滑鼠右鍵按一下新建立的書籤，然後選取「編輯 URL」。
5. 將程式碼片段貼入文字欄位，然後點擊 Enter。

#### Safari

Safari無法手動建立書籤小程式，但書籤URL可以編輯成書籤小程式。

1. 按一下右上方的共用圖示，開啟書籤強制回應視窗。
2. 將書籤命名為「Adobe Experience Cloud Debugger」，並儲存在所需位置。
3. 按一下書籤 > 編輯書籤，並找出新建立的書籤。
4. 以滑鼠右鍵按一下，再按一下編輯位址，然後將程式碼片段貼入文字欄位。

## 使用舊版除錯程式

導覽至您網站上所要的頁面，然後按一下書籤小工具。 隨後出現的快顯視窗中，會顯示傳送至 Adobe 的資料。

> [!NOTE] 某些廣告封鎖外掛程式和快顯視窗封鎖程式可能會干擾除錯程式視窗的載入。請檢查瀏覽器中遭封鎖的快顯視窗，並允許除錯程式顯示，以利其正常運作。

除錯程式有數個可用選項，所有選項都可自訂資料的顯示方式。這些選項都不會影響資料收集。

* **顯示的 Experience Cloud 產品**: 顯示或隱藏每個 Experience Cloud 產品的影像要求。
* **URL 解碼**: URL 會解碼影像要求，以便符合報表中顯示的內容。Adobe 建議您維持此方塊的勾選狀態。
* **自動重新整理**: 每隔幾秒自動重新整理快顯視窗，藉此檢查頁面上是否有其他影像要求。如果您需要在除錯程式中複製/貼上內容，請停用自動重新整理，以便保留您的選項。
* **易記格式**: 將顯示格式切換為實用標籤或影像要求的原始查詢字串。如需詳細資訊，請參閱[資料收集查詢參數](query-parameters.md)。

若要儲存除錯程式的預設顯示選項，請在右上角的「Adobe 除錯程式」連結上按一下滑鼠右鍵，然後複製連結位址。編輯您目前的除錯程式書籤小程式，並將更新後的程式碼片段貼到 URL 欄位。
