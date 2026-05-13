---
description: 瞭解異常偵測及其計算方式。
title: 如何使用異常偵測自動尋找趨勢
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
feature: Report Builder
role: User, Admin
exl-id: 6e3881c8-3e1c-4df8-ba38-e8bc84cfc3d4
TQID: https://experienceleague.adobe.com/P2dvU8YgWcjCZ6h4oTxK-2-z1X3-wl-oMp70UIJGeXo
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: c67272a6-888e-425e-9e97-a87304637eed
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: f1f1a2d4-0976-4881-b091-c2bb8de7ffac
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 511
ht-degree: 18%

---

# 異常偵測{#anomaly-detection}

{{legacy-arb}}

異常偵測使用統計模型來自動尋找資料中的意外趨勢。 此模型會分析量度並決定上下界限和值的預期範圍。 當發生意外的尖峰或下降時，系統會在報告中發出警報。

您可能會調查的異常例子包括：

* 平均訂購值的劇烈下降
* 訂單激增但低收入
* 試用版註冊數量激增或下降
* 登陸頁面檢視次數下降
* 視訊緩衝事件中的Spices
* 低影片位元速率激增

>[!NOTE]
>
>異常偵測僅限於選取「日」顆粒度時適用。

<p class="head"> <b>異常偵測量度</b> </p>

異常偵測會為您選取的每個量度新增量度值，包括：

<table id="table_BF75FC874634498DB6632C12CBD8D533"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 下限 </td> 
   <td colname="col2"> <p>預測間隔的較低層級。 低於此層級的值會視為異常。 </p> <p>表示值在此層級以上的95%信賴度。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 預期 </td> 
   <td colname="col2"> <p>根據資料分析的預測值。 這個值也是上下邊界之間的中間點。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 上限 </td> 
   <td colname="col2"> <p>預測間隔的上層。 高於此層級的值會視為異常。 </p> <p>表示有95%的把握值會低於此等級。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Report Builder會將這些值套用至選取的量度。 例如，如果您選取「頁面檢視」量度並套用異常偵測，則會使用&#x200B;*`Page Views Lower Bound`*&#x200B;量度。

**異常偵測的計算方式**

異常偵測使用訓練時段來計算、學習和報告每天的預測間隔資料。 培訓期間是歷史期間，可識別正常與異常的內容，並將學到的內容套用至報告期間。 在行銷報表中，提供30、60和90的培訓期。 在Report Builder中，30天可供使用。

培訓期間不一定與所選的報告期間相同。 報表圖表會顯示您在行事曆中指定的日期範圍期間。

若要計算資料，會使用下列各演演算法，將每個量度的每日總計與培訓期間進行比較：

* Holt Winters乘法（三指數平滑化）
* Holt Winters加性（三重指數平滑處理）
* 已修正的保持區趨勢（雙指數平滑處理）

每個演演算法都會套用，以判斷具有最小平方誤差總和(SSE)的演演算法。 然後會計算「平均絕對百分比誤差(MAPE)」和目前的「標準誤差」，以確定模型是否在統計上有效。

這些演演算法可以延伸，以提供未來期間量度的預測預測。

由於培訓期間依報告期間開始而異，因此您可能會看到針對同一日期（屬於兩個不同期間的一部分）報告的資料差異。

例如，如果您執行1月1日至14日的報表，然後執行1月7日至21日的報表，您可能會在1月7日至14日的兩個不同報表中，看到相同量度不同的預測資料。 這是訓練期間差異的結果。

| 報告範圍 | 訓練時段 |
|--- |--- |
| 1月1-14日 | 11月27日至12月31日 |
| 1月7-21日 | 12月4日至1月6日 |
