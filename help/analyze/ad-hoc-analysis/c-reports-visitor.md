---
description: 顯示訪客的相關資訊，包括訪客計數、客戶忠誠度和訪客特性等。
title: 訪客報表
topic: Ad hoc analysis
uuid: 3e9b41d1-d6ff-47a8-aa6b-829df1040c34
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 訪客報表

顯示訪客的相關資訊，包括訪客計數、客戶忠誠度和訪客特性等。

## 回訪頻度 {#concept_447A99B71E484D27A7A02888CC51FD3D}

顯示來自舊訪客的瀏覽與屬於每個時間長度類別的瀏覽之間所經過的時間長度。 使用報告可以查看回頭訪客未瀏覽您網站的平均時間，以及回頭客戶的趨勢。

<!-- 

c_reports_return_freq.xml

 -->

例如，在此報告中顯示「訂購」度量，可協助零售網站了解瀏覽間產生轉換的最有效時間。使用這些資訊可有效行銷一段時間未瀏覽您網站的訪客。

您可以：

* 識別回訪訪客數量和回訪頻度。
* 評估您網站對訪客的吸引力和相關性。
* 了解您網站對訪客的吸引力以及他們迫切希望回訪網站以進一步互動或檢視更新內容的頻率。
* 識別網站內容和促銷活動對訪客的影響。

依預設，此報表具有下列時間長度：

* 少於一天
* 一至三天
* 三至七天
* 七至十四天
* 十四天至一個月
* 超過一個月

## 訪問次數 {#concept_BBB614072FD74379B1A8520ACB75AE9A}

顯示網站上哪些客戶瀏覽次數對成功度量影響最大。 首次瀏覽您網站的訪客會計入「瀏覽次數1」行項目。 再次瀏覽網站的訪客會計入「瀏覽次數2」行項目，依此類推。

<!-- 

c_reports_visit_number.xml

 -->

您可將此報表當做流失報表使用，以查看訪客是否正在回訪。 您也可以新增收入度量，以查看您是否從初始瀏覽或後續瀏覽產生更多收入。

例如，此報表可以回答下列問題：在第四次瀏覽才購買的客戶所產生的收入，是否多於在第一次瀏覽即購買的客戶？

您可以依其他報表或變數劃分此報表，用以判斷：

* 一個使用者點進促銷活動XYZ進行購買通常需要多少次瀏覽。
* 在產生銷售機會前，東京 (舉例來說) 的使用者是否比倫敦的使用者需進行更多次瀏覽。

>[!NOTE] 若同一訪客在相同時段內瀏覽您的網站多次，則每瀏覽一次，每個指定的訪問次數都會隨之增加。

此報表以訪客每次點擊傳遞至Adobe的訪客ID資料為基礎。 收到這些資料時，Adobe 會與歷史訪客 ID 資料進行比較，判斷這次點擊是否為：

* 新訪客（瀏覽次數等於1）。
* 繼續瀏覽的先前訪客（瀏覽次數不會增加）。
* 進行新瀏覽的先前訪客（瀏覽次數增加一）。

>[!NOTE]每個 Analytics 訪客 ID 都與 Adobe 伺服器上的訪客資料相關聯。無論訪客 ID Cookie 過期與否，訪客閒置最少 13 個月就會刪除其訪客資料。

## 客戶忠誠度 {#concept_991F758BAA304B7B9D48BD73BBB62FE5}

使用此報表可查看新客戶和常客，誰對您的收入影響比較大。

<!-- 

c_reports_customerloyalty.xml

 -->

The [!UICONTROL Customer Loyalty] report displays purchasing patterns of customers based on four categories of loyalty:

* **不是客戶**：從未購買過的訪客
* **新客戶**：購買過 1 次的訪客
* **回頭客戶**：購買過 2 次的訪客
* **忠實客戶**：購買次數 3 次以上的訪客

>[!NOTE] 使用這些度量時，無論造訪期間 (或訪客) 是否購買，所有使用者造訪 (或所有訪客) 都會顯示在報表中。

在發生購買事件的瀏覽結束後，忠誠度狀態會變更。 例如，新客戶（1次購買）進行購買，然後在購買後於同次瀏覽中註冊電子報。 則該電子報註冊事件仍視為「新客戶」互動，因為訪客的客戶忠誠度狀態將於下次造訪時才會變更。

## 訪客資料 {#concept_4D829198CD144DCDA667E0651F93AFC7}

顯示您網站訪客類型的相關資訊。 您可以看到訪客的位置、所使用的瀏覽器類型和電腦硬體、所使用的語言，以及訪客的網際網路服務供應商資料等。

<!-- 

c_reports_visitor_profile.xml

 -->

**[!UICONTROL Languages]**:顯示訪客的慣用語言、擷取預設瀏覽器語言，並顯示訪客在您網站上最常使用的語言。

**[!UICONTROL Domains]**:列出訪客存取您網站時使用的組織和ISP。 This report differs from the [!UICONTROL Full Domains] report in that the Full Domains report registers the full ISP domain, whereas this report lists the secondary domain.

**[!UICONTROL Top Level Domains]**:根據原始網域的副檔名識別訪客所屬的世界各地，並顯示來自這些國家的訪客數量。 以。com、.net、.edu、.gov和。org結尾的網域通常位於美國，並與其他網域分開列出。

**[!UICONTROL Visitor ZIP/Postal Code]**:顯示對購買成功度量影響最大之客戶的郵遞區號。

## 地域劃分 {#concept_7C1B930F90F945B49205D3855CAE1813}

<!-- 

c_reports_geosegmentation.xml

 -->

即時顯示訪客的地理動態，包括其瀏覽的國家、州和城市。 您也可以獲得有關網站受眾技術與偏好的重要深入資訊。
