---
description: 將協力廠商應用程式的追蹤資料匯入 Analytics。
title: 開始使用 Analytics Data Connectors
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Data Connectors 概觀

Adobe為組織提供可操作的即時智慧，以瞭解其數位策略和行銷計畫。 資料連接器可讓您將第三方應用程式的追蹤資料匯入Analytics，以便從一個集中位置收集和使用資料。 如果您使用其中一種合作夥伴產品，您可以建立整合，將應用程式資料匯入行銷報告。 整合後，您就可產生包含應用程式資料的報表。

例如，電子郵件整合可能想要使用電子郵件合作夥伴來散發電子郵件促銷活動。 當訪客造訪您的網站時，您會想知道哪些訪客是因您的電子郵件促銷活動而來。 資料連接器將電子郵件合作夥伴的資料整合到行銷報告中，讓您能夠判斷這些資訊，以評估電子郵件宣傳的成效。

**系統要求**

資料連接器應與最常用的瀏覽器適當整合。 不過，在符合下列建議的系統上，報表的外觀和功能最佳：

* 瀏覽器：Microsoft Internet Explorer 6及更新版本
* Cookie：必要
* JavaScript：啟用
* 作業系統：Windows架構
* Macromedia Flash Player:第6版或更新版本
* 螢幕解析度：1024x768（800x600將可使用）
* 色彩深度：16位元或更高版本

此外，使用者的網頁瀏覽器啟用 JavaScript 時，可改善資料收集效能。

**必備條件**

在為產品設定資料連接器整合之前，請執行下列動作：

* 擁有合作夥伴產品帳戶的必要存取認證，並擁有存取您要與行銷報告整合之所有資料的權限。 您可能想要為報表發佈者建立特殊的電子郵件帳戶，並通知有關整合作業的資訊。
* 識別包含促銷活動資訊的自訂變數。 這通常稱為促銷活動追蹤代碼，但您的組織可能會使用某些其他術語。
* 決定您要接收印象的事件，然後按一下資料。 您可能會想據以重新命名事件。
* 將適當的程式碼放在您的登陸頁面上，讓Analytics能夠針對來自合作夥伴產品的資料進行適當的模型建立。 各夥伴產品的具體說明請參閱「資源」標籤上 Data Connectors 精彩案例中的內容。

## 新增整合

您必須使用有效的帳戶才能存取 [!UICONTROL Data Connectors] 登陸頁面 (主控台)。此外，建議您先熟悉 Adobe Analytics 的操作。

1. 登入 Adobe Experience Cloud。
1. 按一下 **[!UICONTROL Analytics]** > **[!UICONTROL Admin]** > **[!UICONTROL Data Connectors]**.
1. 按一下 **[!UICONTROL Add New]**.
1. 逐步執行介 **[!UICONTROL Add Integration]** 面。

   由於各項產品整合不盡相同，因此在整合過程中您可能需要提供特定的設定資訊。

   整合完成時，合作夥伴產品圖示會顯示在「Data Connectors 網路」頁面上，且可在功能表中取用。

## Data connectors 主控台

啟用整合後，會顯示在 [!UICONTROL Data Connectors] 頁面上。您可以在主控台上檢視詳細資訊及變更設定。您可以檢視公司內所有報表套裝的作用中整合和整合。 您也可以檢視活動記錄、將整合設為控制面板、設定整合，以及尋找說明。

![Data Connectors 主控台](assets/data-connectors-console.png)

## Data Connectors 中的再行銷區段

再行銷區段是根據 Data connectors 整合中所使用之變數建立的資料檔案。

Adobe Analytics 會透過 Data Warehouse 將這些檔案分為每日檔案，傳送至 Adobe 為第三方建立的 FTP。然後，協力廠商會將這些檔案分發給用戶端。 公司通常會使用這些工具，將產品重新行銷給可能曾造訪過網站並看過產品卻並未購買的公司。 （例如，您聯絡客戶，針對他們檢視的產品提供折扣，但最終並未購買）。

**區段**

* [!UICONTROL Cart Abandonment]:訪客新增項目至購物車但未購買的百分比。 技術上，它是由「訂購」除以「購物車新增」所組成的計算量度。
* [!UICONTROL Purchases]:根據特定產品中的訊息ID購買的收件者ID（或訪客ID）。
* [!UICONTROL Product Views]:類似於 [!UICONTROL Cart Abandonment]，這也是計算度量。 It reports [!UICONTROL Product Views] divided by Orders, because customers&#39; viewing the product shows some interest.

**實施範例**

若要成功實作再行銷區段，必須符合下列條件：

* 資料連接器合約已經建立，您的組織已與Adobe顧問完成實施階段。
* 在產品變數的同時引發對應事件：
   * 放棄購買：`scAdd` 事件
   * 購買：`purchase` 事件
   * 產品檢視：`prodView` 事件

>[!NOTE] 如果定義產品時沒有關聯事件，則會自動引發 prodView 事件。如果上述要求不符合，則對應的再行銷區段無法正確回報。

[!UICONTROL Cart Abandonment]:在使用者將產品新增至購物車後引發：

```
s.products=";cat";
s.events="scAdd";
```

[!UICONTROL Purchases]:在購買確認頁面上引發：

```
s.products=";
cat;1;50";
s.events="purchase";
//Note: Though optional, adding the purchaseID variable increases accuracy by preventing duplicate purchases
```

**常見問題**

| 問題 | 說明 |
| -----------| ---------- |  
| 再行銷區段檔案中未顯示產品ID資訊。 | 正確的事件啟動時，就會發生此狀況，但相同的影像要求上沒有產品變數存在。為了修正此問題，請確定產品變數和對應的事件會在相同頁面上觸發，如上述實作範例所示。 |
| 未收到重新行銷區段檔案。 | 如果您未收到檔案，請讓組織的受支援使用者之一聯絡ClientCare，以調查未成功收到報表的原因。 |


>[!IMPORTANT] 除了您的標準 Data Connectors 整合的再行銷區段檔案外，通常顧問也會設定 Data Warehouse 要求作為每日排程報表。此資料倉庫請求將包含資料連接器變數和非資料連接器變數，且只能根據組織的特定請求排程請求。 若要避免疑難排解時產生混淆，請指定相關檔案是實際的再行銷區段檔案，還是包含非Genesis變數的資料倉庫請求。
