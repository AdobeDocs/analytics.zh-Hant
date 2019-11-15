---
description: 安裝舊版Adobe Experience cloud除錯程式。 此除錯程式會檢查Analytics、Target、Advertising Cloud、Identity Service、DTM和Launch的標籤。
title: 舊版Adobe Experience cloud除錯程式
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 舊版Adobe Experience cloud除錯程式

> [!IMPORTANT] 此除錯工具不再受維護。 Adobe建議改用 [Adobe Experience cloud除錯程式Chrome擴充功能](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)。

舊 [!UICONTROL 版除錯程式] 會檢查大部分Adobe Experience cloud服務的標籤。 使用除錯程式可讓您查看網站上任何指定頁面上的Adobe資料。 您可使用此資訊來疑難排解或驗證組織的實施。

## 安裝舊式除錯程式

建立JavaScript書籤小程式以安裝除錯程式。

### 步驟1:複製書籤小程式碼

將下列程式碼複製到剪貼簿：

```JavaScript
javascript:void(window.open("","stats_debugger","width=800,height=800,location=0,menubar=0,status=1,toolbar=0,resizable=1,scrollbars=1").document.write("<script language=\"JavaScript\" id=dbg src=\"https://www.adobetag.com/d1/digitalpulsedebugger/live/DPD.js\"></"+"script>"+"<script language=\"JavaScript\">window.focus();</script>"));
```

### 步驟2:將書籤小程式碼貼入書籤

每個瀏覽器處理書籤的方式不同，但概念相同。 以所要的名稱和書籤小程式碼建立書籤作為URL。

#### Chrome

如果您堅持不使用 [chrome擴充功能](https://docs.adobe.com/content/help/en/debugger/using/experience-cloud-debugger.html)，則可改用舊版除錯程式書籤小工具。

1. 按一下右上方的三個點，然後前往「書籤&gt;書籤管理員」。 您也可以按 `Ctrl` + `Shift` + `O` (Windows)或 `Cmd` + `Shift` + `O` (Mac)。
2. 在書籤管理員的右上方，按一下三個點，然後按一下「新增書籤」。
3. 在「名稱」欄位中，將其標示為「Adobe Experience Cloud除錯程式」，然後將程式碼片段貼入URL欄位。
4. 使用書籤管理員，將新的書籤小程式置於所需位置。

#### Firefox

1. 按一下右上方的三行，然後前往「資料庫&gt;書籤&gt;顯示所有書籤」。 您也可以按 `Ctrl` + `Shift` + `B` (Windows)或 `Cmd` + `Shift` + `B` (Mac)。
2. 按一下「組織&gt;新書籤」。
3. 在「名稱」欄位中，將其標示為「Adobe Experience Cloud除錯程式」，然後將程式碼片段貼至「位置」欄位。 「標籤」和「關鍵字」欄位不是必要欄位。
4. 使用資料庫視窗，將新的書籤小工具置於所需位置。

#### Edge

Edge無法手動建立書籤小工具，但可編輯書籤URL。

1. 按一下URL欄位右側的星形圖示，將目前頁面加入書籤。
2. 將書籤命名為「Adobe Experience Cloud Debugger」，並將其儲存在所需位置。
3. 按一下含有線條的星形圖示，以開啟「我的最愛」列。
4. 以滑鼠右鍵按一下新建立的書籤，然後選取「編輯URL」。
5. 將程式碼片段貼入文字欄位，然後按Enter。

#### Safari

Safari無法手動建立書籤小程式，但可編輯書籤URL。

1. 按一下右上方的「共用」圖示，開啟書籤模式視窗。
2. 將書籤命名為「Adobe Experience Cloud Debugger」，並將其儲存在所需位置。
3. 按一下「書籤&gt;編輯書籤」，並找出新建立的書籤。
4. 以滑鼠右鍵按一下&gt; 「編輯位址」，然後將程式碼片段貼入文字欄位。

## 使用舊版除錯程式

若要使用除錯程式，請導覽至您網站上所要的頁面，然後按一下書籤小工具。 出現快顯視窗，顯示傳送至Adobe的資料。

> [!NOTE] 某些廣告封鎖外掛程式和快顯封鎖程式可能會干擾除錯程式視窗的載入。 檢查瀏覽器中是否有已封鎖的快顯視窗，並允許它們，讓除錯程式可正常運作。

除錯程式有數個可用選項，所有選項都可自訂資料的顯示方式。 這些選項均不會影響資料收集。

* **** 顯示的Experience cloud產品：顯示或隱藏每個Experience cloud產品的影像要求。
* **** URL解碼：URL會解碼影像要求，以符合報告中顯示的內容。 Adobe建議勾選此方塊。
* **** 自動重新整理：每隔幾秒自動重新整理快顯視窗，以檢查頁面上是否有更多影像要求。 如果您需要在除錯程式中複製／貼上內容，請停用自動重新整理，讓您的選取範圍維持不變。
* **** 友好格式：在影像請求中的實用標籤和原始查詢字串之間切換顯示格式。 如需詳 [細資訊，請參閱資料收集查詢參數](../js-implementation/data-collection/query-parameters.md) 。

若要儲存除錯程式的預設顯示選項，請在右上角的「Adobe除錯程式」連結上按一下滑鼠右鍵，然後複製連結位址。 編輯您目前的除錯程式書籤小程式，並將更新的程式碼片段貼入URL欄位。
