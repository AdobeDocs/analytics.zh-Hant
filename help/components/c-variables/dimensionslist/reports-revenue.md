---
description: 測量在特定時段內透過您所有的產品所產生的收入金額。
title: 收入
topic: Reports
uuid: e5b72798-f5c7-440d-a62d-376bfd115ac8
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 收入

測量在特定時段內透過您所有的產品所產生的收入金額。

使用「收入」來檢視您網站的常見成功模式與趨勢。您也可以藉此選出網站上特別成功的時段，並找出原因，據以建立往後的促銷活動。

## 報告的一般屬性 {#section_97FC92DFB07D45A79F40B452F9AEE57B}

* 要讓此報告成功收集資料，必須符合若干需求。下列項目必須產生於相同的影像要求中：

   * 事件 [!UICONTROL purchase] 必須在變數中 `s.events` 觸發。

   * 必須以價格欄位中的數字定義 `products` 變數。
   * 在下列範例中，收入報告中會傳入 $35.99：

      ```js
       s.products="Mens;Shoes;1;35.99"
      ```

      ```js
       s.events="purchase"
      ```

* 若 [!UICONTROL s.products] 變數中有多項產品存在，則所有產品都將計入收入報告中。以 [!DNL s.products="Mens;Socks;1;4.50,Womens;Socks;1;4.50"] 為例，報表中將會傳入 $9 的收入。

   >[!NOTE]
   >
   >當單一產品的數量增加時，收入金額並不會乘上此數量。以 [!DNL s.products="Womens;Socks;5;4.50"] 為例，傳入報表中的並不是 $22.50，而是 $4.50。請確認您的實作傳入的是所列數量的收入總額 ([!DNL s.products="Womens;Socks;5;22.50"])。

* [!UICONTROL Revenue] 將某個時段的總金額四捨五入為最接近的貨幣值。 它不會四捨五入個別的產品或點擊。
* 由於 Analytics 會將每天的金額四捨五入到最接近的整數貨幣值，因此在比較每天加總起來的金額與每月總額時，可能會略有差異。這是因為每月總額並非每天四捨五入後加總的金額，而是四捨五入到最接近之整數貨幣值的絕對總額。
* 您可以建立不會將收入四捨五入到最接近之整數貨幣值的報告，方法是使用[計算量度](https://docs.adobe.com/content/help/zh-Hant/analytics/components/calculated-metrics/cm-overview.html)。
* 除非使用 `purchaseID` 變數，否則重新整理頁面的使用者會多次將這個資料傳送到 Adobe，導致收入膨脹。
* 以小時為單位的劃分會以報表套裝的時區為準。
* 此報告不含明細項目。它只能以趨勢格式來檢視。
* 詳細程度可採用小時、日、週、月、季與年。這些詳細程度是否可用須取決於報告日期範圍。
* 此報告可依下列報告進行劃分 (視組織與報表套裝設定而定)：

   * [!UICONTROL Time Spent per Visit] 報告.
   * [!UICONTROL Pages and Site Sections] 報告.
   * [!UICONTROL Videos] 報告.
   * [!UICONTROL Page Depth and Entry Pages] 報告.
   * 大部分 [!UICONTROL Traffic Sources]報表，包括 [!UICONTROL Search Keywords]、 [!UICONTROL Search Engines]和報 [!UICONTROL Referring Domains] 表。

   * [!UICONTROL Tracking Code] 報表和所有關聯的分類報表。
   * [!UICONTROL Products variable] 報表和所有關聯的分類報表。 也可 [!UICONTROL Categories] 以報告。

   * 幾乎所有 [!UICONTROL Visitor Profile] 報表，排除 [!UICONTROL GeoSegmentation] 報表。

   * 所有具 [!UICONTROL Custom Conversion] 有基本子關聯的變數報表。

* 劃分無法以小時為單位。

## 產品特定屬性 {#section_ED87FFD020634453AABE86B0248BE69B}

* 此報告可從 **[!UICONTROL Conversion]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* [!UICONTROL Traffic Sources] 劃分可在下方找 [!UICONTROL Finding Methods]到。

* 此報告可從 **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* 除了所有先前列出的劃分外，還 [!UICONTROL First and Last Touch Marketing Channel] 有可用的劃分。

* 此報告可從 **[!UICONTROL Site Metrics]** > **[!UICONTROL Purchases]** > **[!UICONTROL Revenue]**.

* In addition to the previously mentioned breakdowns, [!UICONTROL List]variables and the current [!UICONTROL Video] variables can be used.

* 此報告可使用區段。

* 您可依所有其他報告與變數來劃分此報告中的每個項目，讓您以任何想要的詳細程度檢視劃分內容。
* 您可以搭配使用 [!UICONTROL conversion] 所有 [!UICONTROL traffic] 和度量 [!UICONTROL Revenue]。 You can use different allocation for all [!UICONTROL conversion] metrics.

* 此報告可使用多個高度進階區段。

若此報告未在指定位置中，請洽詢您的管理員。他們可能變更了預設的名稱或功能表結構，以因應您的組織獨特的需求。
