---
title: 歸因模型與回顧期間
description: 不同類型的歸因將評分分配給維度項目的方式。
feature: Attribution
role: User, Admin
exl-id: f36de41e-1c53-477d-b326-528fbd4ec9ec
source-git-commit: 08e29da4847e8ef70bd4435949e26265d770f557
workflow-type: tm+mt
source-wordcount: '1603'
ht-degree: 94%

---

# 歸因模型與回顧期間

Adobe Analytics 中的歸因概念需要兩個元件：

* **歸因模型：**&#x200B;模型用於描述群組中點擊的轉換分佈方式。例如首次接觸或上次接觸。
* **屬性回顧期間：**&#x200B;回顧期間則描述每個模型中點擊的分類方式。例如造訪或訪客。

## 歸因模型

| UI 圖示 | 歸因模型 | 定義 | 使用時機 |
| --- | --- | --- | --- |
| ![上次接觸](assets/last_touch1.png) | 上次接觸 | 會將 100% 的評分給予轉換前發生的最近一次接觸點。 | 最基本也最常用的歸因模型。這類模型常用於考慮週期較短的轉換。上次接觸通常由管理搜尋行銷或分析內部搜尋關鍵字的團隊使用。 |
| ![首次接觸](assets/first_touch.png) | 首次接觸 | 會將 100% 的評分給予歸因回顧期間中首個出現的接觸點。 | 這是另一種常見的歸因模型，可用於分析意圖提升品牌知名度或客戶贏取量的行銷管道。這是「顯示」或「社交」行銷團隊常用的模型，但也非常適合用於評估現場產品的推薦成效。 |
| ![同一次接觸](assets/same_touch.png) | 同一次接觸 | 會將 100% 的評分給予轉換發生當下的點擊。如果接觸點並未在同一次點擊化為轉換，就會歸類在「無」當中。 | 這個模型很適合用於評估轉換時立即顯示的內容或用戶體驗。「產品」或「設計」團隊經常會使用此模型來評估轉換發生的頁面帶來的成效。 |
| ![線性](assets/linear.png) | 線性 | 會將相等的評分歸給每個帶來轉換的接觸點。 | 對於具有較長考量週期的轉換，或需要更頻繁進行客戶參與的用戶體驗，這個模型非常實用。想要評估行動應用程式通知效果或訂閱型產品的團隊，通常會使用這種模型。 |
| ![U 形](assets/u_shaped.png) | U 形 | 會將 40% 的評分給予第一次互動，再將 40% 的評分給予上次互動，剩下的 20% 則分給兩者之間的任何接觸點。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的轉換，兩者會平均獲得 50% 的評分。 | 如果您想要評估帶來轉換的互動，或雖然該次轉換已關閉，但仍想找出帶來助力的互動，這個模型非常理想。如有團隊習慣採取較為均衡的方法，但同時想要將大部分評分歸給發現或關閉轉換的管道，通常會使用 U 形歸因。 |
| ![J 形](assets/j_shaped.png) | J 形 | 會將 60% 的評分給予上次互動，再將 20% 的評分給予第一次互動，剩下的 20% 則分給兩者之間的任何接觸點。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的轉換，上次互動會獲得 75% 的評分，第一次則獲得 25%。 | 如果您想將評分優先歸給發現與關閉轉換的互動，但以後者為主，這個模型非常合適。如有團隊習慣採取較為均衡的方法，但同時想將大部分評分給予關閉轉換的管道，通常會使用 J 形歸因。 |
| ![反向 J 形](assets/inverse_j.png) | 反向 J | 會將 60% 的評分給予第一個接觸點，再將 20% 的評分給予上個接觸點，剩下的 20% 則分給兩者之間的任何接觸點。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的轉換，第一次互動會獲得 75% 的評分，上次則獲得 25%。 | 如果您想將評分優先歸給發現與關閉轉換的互動，但以前者為主，這個模型非常合適。如有團隊習慣採取較為均衡的方法，但同時想將大部分評分給予啟動轉換的管道，通常會使用反向 J 形歸因。 |
| ![自訂](assets/custom.png) | 自訂 | 可指定要將多少權重歸給第一個接觸點、最後一個接觸點以及兩者之間的任何接觸點。如果您輸入的自訂數字加總並非 100，系統也會將指定值標準化為 100%。只有單一接觸點的轉換則會獲得 100% 的評分。如果是具有兩個接觸點的互動，系統會忽略中間參數，然後將第一和最後一個接觸點標準化為 100%，再按照設定分配評分。 | 如果您想要完整控制歸因模型，且具有其他歸因模型無法滿足的特定需求，這個模型最理想。 |
| ![時間耗損](assets/time_decay.png) | 時間耗損 | 會以自訂的半衰期參數 (預設為 7 天) 進行指數耗損。每個管道的權重須視接觸點啟動和最終轉換之間所經過的時間量而定。用於判斷評分的公式為 `2^(-t/halflife)`，`t` 代表接觸點和轉換之間的時間量。 所有接觸點隨後都會標準化至 100%。 | 團隊如果經常刊登影片廣告，或針對預定日期的活動進行行銷，這個選項相當合適。從行銷活動到發生轉換的時間越久，獲得的評分就越少。 |
| ![參與率](assets/participation.png) | 參與率 | 會將 100% 的評分給予所有不重複接觸點。相較於其他歸因模型，這項模型的轉換總數會經過誇大。參與率不會計入重複出現多次的管道。 | 這個模型很適合用於了解客戶經常接觸到哪些特定互動。媒體組織經常會使用此模型來計算內容速度。零售組織則常會使用此模型來瞭解網站的哪些部分是帶來轉換的關鍵。 |
| ![演算法](assets/algorithmic.png) | [演算法](algorithmic.md) | 使用統計技巧動態決定所選量度的最佳評分配置。 | 為貴公司選擇正確的歸因模型時，有助於避免猜測或試探。 |

## 回顧期間

回顧期間是指轉換要納入接觸點時需要回顧的時間量。會將較多評分給予第一次互動的歸因模型，會在不同回顧期間中顯示出較大的落差。

* **造訪回顧期間：**&#x200B;回顧至轉換發生當下該次造訪的開始。造訪回顧期間較窄，因為造訪之前的時間皆不計入。造訪回顧期間會遵照虛擬報表套裝中修改的造訪定義執行。

* **訪客回顧期間：**&#x200B;回顧至目前日期範圍當月 1 日以來的所有造訪。訪客回顧期間較寬，因為可計入多次造訪。訪客回顧會考量報表日期範圍當月 1 日以來的所有值。舉例來說，如果報表日期範圍為 9 月 15 日到 9 月 30 日，則訪客回顧日期範圍將是 9 月 1 日到 9 月 30 日。

* **自訂回顧期間：**&#x200B;可讓您將歸因期間擴展至報告日期範圍以外，最多 90 天。系統會對報告時段內的每個轉換評估自訂回顧期間。例如，對於2月20日發生的轉換，10天的回顧期間將會在歸因模型中評估2月10日至2月20日的所有維度接觸點。

>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [自訂回顧視窗](https://video.tv.adobe.com/v/36204?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


## 範例

考量下列範例：

1. 9 月 15 日當天，某個訪客透過付費搜尋廣告前往您的網站後離開。
2. 9 月 18 日當天，該訪客透過來自朋友的社交媒體連結再次造訪您的網站。對方在購物車中加入數個商品，但並未購買任何商品。
3. 9 月 24 日當天，您的行銷團隊會寄送電子郵件給對方，郵件內含對方購物車中某些商品的優惠券。對方使用了抵用券，但也造訪了數個其他網站，看看是否有其他優惠券可用。對方透過顯示廣告找到了其他優惠券，最終以 $50 美元的價格購買商品。

根據您的回顧期間和歸因模型，管道會獲得不同的評分。以下為幾個值得了解的範例：

* 如果採用&#x200B;**「首次接觸」** 和&#x200B;**「造訪回顧期間」**，歸因只會計入第三次造訪。在電子郵件和顯示廣告兩者之間，訪客優先接觸到電子郵件，因此電子郵件在這次 $50 美元的購買動作中有 100% 的評分。
* 如果採用&#x200B;**「首次接觸」** 和&#x200B;**「訪客回顧期間」**，歸因會計入全部三次造訪。付費搜尋是第一次接觸，因此在這次 $50 美元的購買動作中有 100% 的評分。
* 如果採用&#x200B;**「線性」**&#x200B;和&#x200B;**「造訪回顧期間」**，評分會由電子郵件和顯示廣告平分，兩個管道各有 $25 美元的評分。
* 如果採用&#x200B;**「線性」**&#x200B;和&#x200B;**「訪客回顧期間」**，評分會由搜尋付費、社交媒體、電子郵件和顯示廣告平分，每個管道在這次購買中各有 $12.50 的評分。
* 如果採用&#x200B;**「J 形」**&#x200B;和&#x200B;**「訪客回顧期間」**，評分會由搜尋付費、社交媒體、電子郵件和顯示廣告拆分，
   * 60% 歸給顯示廣告，價值 $30 美元，
   * 20% 歸給付費搜尋，價值 $10 美元，
   * 剩下的 20% 平分給社交媒體和電子郵件，各為 $5 美元。
* 如果採用&#x200B;**「時間耗損」**&#x200B;和&#x200B;**「訪客回顧期間」**，評分會由搜尋付費、社交媒體、電子郵件和顯示廣告拆分。以預設的 7 天半衰期計算，結果如下：
   * 顯示廣告接觸點與轉換之間的間隔為 0 天。`2^(-0/7) = 1`
   * 電子郵件接觸點與轉換之間的間隔為 0 天。`2^(-0/7) = 1`
   * 社交媒體接觸點與轉換之間的間隔為 6 天。`2^(-6/7) = 0.552`
   * 付費搜尋接觸點與轉換之間的間隔為 9 天。`2^(-9/7) = 0.41`
   * 將這些值標準化會產生下列結果：
      * 顯示廣告：33.8%，價值 $16.88 美元
      * 電子郵件：33.8%，價值 $16.88 美元
      * 社交媒體：18.6%，價值 $9.32 美元
      * 付費搜尋：13.8%，價值 $6.92 美元
* 使用&#x200B;**參與率**&#x200B;和&#x200B;**訪客回顧期間**，完整的$50會歸因於付費搜尋、社交、電子郵件和顯示。 如果您以趨勢報表（而非排名報表）來檢視收入，您會在訪客接觸特定行銷管道的個別日期看到每日$50。

>[!TIP]
>
> 如果評分屬於多個管道，其他轉換事件 (例如「訂購」或「自訂事件」) 也會經過拆分。舉例來說，如果兩個管道對某個使用線性歸因模型的自訂事件都有貢獻，則兩個管道各會從自訂事件中獲得 0.5 的評分。這些事件片段在經過所有造訪的加總後，會四捨五入為最接近的整數，顯示於於報表中。
