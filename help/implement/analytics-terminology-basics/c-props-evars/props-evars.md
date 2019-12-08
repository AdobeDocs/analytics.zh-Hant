---
description: 自訂流量變數 (也稱為 prop (s.prop) 或屬性變數) 是一種計數器，會計算每個值傳入 Analytics 中的次數。
keywords: Analytics Implementation;Traffic prop;prop;conversion;evar;s.prop;custom conversion insight;traffic variable
title: Prop 和 eVar 概觀
topic: Developer and implementation
uuid: 522cab2b-1ef8-4f10-b216-c82b21431487
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Prop 和 eVar 概觀

自訂流量變數 (也稱為 prop (s.prop) 或屬性變數) 是一種計數器，會計算每個值傳入 Analytics 中的次數。

在判斷哪些變數應指派至何處時，務必瞭解 Prop 與 eVar 兩者的功能有何差異。瞭解這些差異，可讓您的組織決定最適合使用的變數類型。有關詳細資訊，請參閱[比較 Prop 和 eVar](/help/implement/analytics-terminology-basics/c-props-evars/props-vs-evars.md).

Prop 也可讓您將自訂資料與特定的流量相關事件產生關連。這些變數會嵌入至您的網站上每個頁面中的 [!DNL Analytics] 程式碼中。[!UICONTROL  可透過 ]s.prop[!DNL Analytics] 變數讓您建立專屬於您的組織、產業與企業目標的自訂報表。

例如，若您是汽車製造商，您可能樂見您的「頁面」報表中增添了「最受歡迎車款」這一項內容。配置您其中一個流量屬性來代表車款，即可達成此目的。接著請實施您的程式碼，以將車款傳入至適當頁面上。

> [!NOTE][!DNL Analytics] 最多可支援 75 個 [!UICONTROL s.prop] 變數。

Prop 可用於路徑分析報表或關聯報表。例如，[!UICONTROL 屬性]變數可用來顯示內容類型、子區段或範本名稱。產生的[!UICONTROL 「自訂流量」]報表會顯示最常檢視的內容類型、子區段或範本。

透過自訂流量變數將可解答各式各樣的商業問題，端視您從網站上擷取的內容而定。下列清單包含幾項常見的目標和目的: 

* 瞭解使用者在網站上的導覽路徑
* 瞭解內部使用者搜尋行為
* 依導覽或類別劃分流量
* 依人口統計劃分訪客行為

eVar (或[!UICONTROL 「自訂轉換分析」]變數) 可用來識別特定屬性或動作對於您網站上的成功事件有多少貢獻度。以媒體網站為例，eVar 可用來識別內部促銷吸引訪客進行註冊的效果。當訪客點按內部促銷時，即可使用 eVar 來儲存該促銷的唯一識別碼。當同一名訪客完成註冊，而引發自訂成功事件時，原始唯一識別碼即會獲得該註冊事件的評價。

在轉換網站中，eVar 可用來追蹤登入訪客與非登入訪客完成購買動作的比較。當訪客登入時，eVar 即會設為「登入」。當該名訪客進入結帳頁面時，結帳事件會計入「登入」值中。當訪客在購買後進入「感謝您」頁面時，產品數和購買金額會計入「登入」值中。產生的[!UICONTROL 「自訂 eVar」]報表會顯示「登入」和「非登入」訪客的結帳總數和訂購總數。

如需其他相關資訊，請參閱 Analytics 說明與參考中的[流量變數](https://marketing.adobe.com/resources/help/en_US/reference/traffic_var.html)。

如需在數位標籤管理中設定屬性的相關資訊，請參閱[建立 Web 屬性](/help/implement/c-implement-with-dtm/t-create-web-property.md)。
