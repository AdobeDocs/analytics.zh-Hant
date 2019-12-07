---
description: Experience Cloud 中有數種可用變數。最常見的兩種類型是 Prop 和 eVar，可讓您的組織將標準預設報告所未提供的自訂維度資料報告至您的網站。
keywords: Analytics Implementation;prop;evar;props vs evars;naming convention;traffic variables;persistence;success event;pathing
title: 比較 Prop 和 eVar
topic: Developer and implementation
uuid: 0f02760f-ff69-481c-a817-799f02dafe8e
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 比較 Prop 和 eVar

Experience Cloud 中有數種可用變數。最常見的兩種類型是 Prop 和 eVar，可讓您的組織將標準預設報告所未提供的自訂維度資料報告至您的網站。

在判斷哪些變數應指派至何處時，務必瞭解 Prop 與 eVar 兩者的功能有何差異。瞭解這些差異，可讓您的組織決定最適合使用的變數類型。

**Prop 與 eVar 的比較**

以下是 prop 與 eVar 之間的主要差異:

* **命名慣例**: Prop 會被視為流量變數，也就是說，它們會用來報告您的網站各種維度的使用人氣。eVar 則會被視為轉換變數。它們會用來判斷網站的哪些維度對成功事件有最大的貢獻度。
* **持續性**: Prop 不會在其引發所在的影像要求結束後繼續存留。它們無法與不在相同影像要求中的其他變數產生關聯。而 eVar 則具有持續性。系統會使用一個後端變數來保存原始引發的值，使其能夠讓本身與後續的成功事件產生關聯。
* **成功事件**: 成功事件也稱為轉換事件，是可測量訪客達成目標之次數的量度。舉凡在您的網站上購買商品到訂閱商務通訊，都可作為此事件。eVar 可用來報告轉換事件，以說明哪些值對於訪客達成您的目標最具有正面影響力。流量變數則沒有這項功能。但若您正確設定報告套裝，則可以檢視參與率量度。
* **路徑**: Prop 可使用路徑功能，讓您的組織瞭解使用者在其檢視的變數環境內所採用的指定路徑。Adobe 代表可因應要求啟用路徑功能。eVar 則無法使用路徑功能。
* **潛在可用量度**: prop 與 eVar 之間的可用量度，會隨著變數的設定與資料的平台/版本而大不相同。下列清單列出的是可啟用的項目，而非預設為啟用的項目。如果想要在報告中使用某個量度，但報告中並未列出，請讓您組織的受支援使用者之一聯絡客戶服務。

<table id="table_FB963F60857A4AD79562324FB6F4B6A9"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>量度 </p> </th> 
   <th colname="col2" class="entry"> <p>Prop </p> <p>(流量變數) </p> </th> 
   <th colname="col3" class="entry"> <p>eVar </p> <p>(轉換變數) </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>平均頁面深度 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_165C1BF1574247CEA9190ADCABF79D69" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>平均逗留時間 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_9F0F396E11B442959EC3E5D4D508496D" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>反彈率 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_A268EAF747EA45F8A6A93A1B66667A06" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_09D486144CEA4293A505DCA3F90B82EC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>彈回數 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_471A02B78FD842BB97ED3FF4A5908B03" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D2F11B5687484D9EBF6D1DEB3F303A20" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>計算量度 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_7FAB1CF2ACC44D9198C648D3FC9E52D9" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8BCC2EE92CC04778809D1BD48D2623D7" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>自訂轉換事件 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_D75C764B83AE4491A7E68C459FED1300" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>登入點 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E9A1FCDFCB924D75ABFAEBD5570D4EE0" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5E57974B5A64F3FA3A145428420EB23" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>退出點 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_BE343F94EAD74D54B6ABC80E8A76A9BD" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_3183B2BB62C24B048EDED3295F2BEC85" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>例項 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8733F5AC189E43DAA8D1847416EA68C8" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_B10AB2898F3D4EBA947FADB27B118143" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>頁面檢視 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_8BD2B23FBDA64A648BED40A2993F7C1C" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_CBDFD74340FA4973847033C1F956F0AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>參與率量度 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_E63F978830FB46809E62654F37C4C182" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_6AB756A4598F4452887D29AD4971985A" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>購買量度 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_8F8AB7CD02764245BA73CA1E6B69BAE1" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>重新載入 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_FBE0C84E01004937B7B408198A33A9E7" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>購物車量度 </p> </td> 
   <td colname="col2"> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_123993465D734EABB311730ED03263F6" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>單次存取 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_038C6991E3F341B18E7A355D17C88895" /> </p> </td> 
   <td colname="col3"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>總逗留時間 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_090587D29F1649319033D5A15B34B138" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_841DF09FD32A44B1B1B876F4E0CE29AC" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>不重複訪客 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_38556E6A43B04E2E8A01855452D30A83" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_F5D4BDE1AA9C4C58A6402418390EEC52" /> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>瀏覽 </p> </td> 
   <td colname="col2"> <p><img  src="assets/check-mark.png" id="image_017BB279C5824028870360A5D4D27556" /> </p> </td> 
   <td colname="col3"> <p><img  src="assets/check-mark.png" id="image_2832E346D220429DA643B908EC10260D" /> </p> </td> 
  </tr> 
 </tbody> 
</table>

* **劃分**: Prop 可使用關聯，針對在相同影像要求中引發的其他流量變數顯示頁面檢視。eVar 可使用子關聯，提供有關其他與成功事件相關的轉換變數劃分資訊。

## Prop 或 eVar 的獨特優點 {#section_B384031AB8674065BA5187B0A3A3DAB9}

隨著版本 15 的發行，Prop 和 eVar 的功能差異越來越小。eVar 最近進行了更新，包含將處理負載降至最低的瀏覽/獨特訪客，以及路徑量度。

Prop 擁有幾項優於 eVar 的優點，其中幾項可透過其他方法彌補:

* Prop 資料幾乎可以立即收集並用於報告。eVar 可能需要 30 分鐘以上才會出現在報表套裝資料中。
* 所有 Prop 都能啟用類似流程圖的報表，讓您查看訪客前來您網站所採取的路徑。這些路徑流報表可以同時用於 [!UICONTROL Ad Hoc Analysis] 中的 Prop 和 eVar。
* Prop 可以關聯數個層級，但 eVar 只能 進行一次子關聯。在使用相同資料進行關聯的條件下，透過分段可以減輕這種限制。
* 參與率量度可讓您查看在成功事件之前有哪些 Prop 值參與。

另一方面，eVar 擁有幾項優於 Prop 有限特質的優點:

* eVar 可以使用成功事件做為量度。Prop 不能。
* eVar 有效期可以自訂，包括使用每個點擊的有效期 (不過不是永久值)。Prop 無論如何都無法持續。

路徑量度 (例如總逗留時間、登入點和退出點) 原本無法用於 eVar。不過最近的更新已讓這些量度可供用於 eVar，提高了 eVar 的價值。

## 適用項目 {#section_022D016A4EEB45179A15BFF044A261A4}

**Prop:** 若您最擔心的是延遲，而且只想使用此維度測量流量 (而非成功事件)。

**eVar:** 若您最擔心的是資料劃分與關係。

>[!TIP]
>
>若不希望 eVar 永久存在，您可將其有效期變更為「點擊」，如此就不會保留資料超過點擊期限。

