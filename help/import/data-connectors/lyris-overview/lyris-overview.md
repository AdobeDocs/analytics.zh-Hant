---
description: 說明透過整合所實現的行銷效率。
title: Adobe Analytics 的 Lyris Data Connector
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Adobe Analytics 的 Lyris Data Connector{#lyris-data-connector-for-adobe-analytics}

說明透過整合所實現的行銷效率。

Adobe® Data Connectors™ 電子郵件整合結合 Adobe Analytics 的行為資訊與 Lyris 電子郵件行銷功能，透過更相關的傳訊重新定義成功測量及鎖定受眾。

向這些市場區塊傳遞相關電子郵件訊息可帶來全新的收入商機，進而推動全新和現有電子郵件促銷活動的轉換和收入。舉例來說，根據瀏覽期間檢視的產品或放棄的購物車中的產品來傳送相關電子郵件訊息，經證明對收入有顯著影響，而且對成本的影響最小，因為這只是運用您網站已獲得的訪客。

這種行銷效率的提升，是整合 Adobe Analytics 與 Lyris 的主要優點之一。此外，這項整合會自動將電子郵件量度與 Adobe Analytics 資料同步化，封閉迴圈報表的同步頻率可達每小時一次。

## 主要優點和功能{#key-benefits-and-features}

說明結合 Lyris 與 Adobe Marketing Reports &amp; Analytics 的主要優點。

Lyris 與 Adobe Analytics 間的整合提供下列主要優點：

* 將電子郵件行銷與分析資料整合至單一報表介面
* 透過轉換和對收入和網站成功的貢獻，最佳化電子郵件促銷活動。
* 根據動態行銷區段，再行銷關鍵訪客和市場區塊

### 動態行銷區段

電子郵件整合支援動態行銷區段，可協助您推動業務發展。這項整合具備下列立即可用的行銷區段：

* **放棄購買設定檔**：透過專為猶豫是否要完成購買購物車項目的訪客量身打造的微調促銷活動，協助將訪客轉化為客戶
* **購買設定檔**：透過鎖定訪客購買模式為目標的促銷活動，增加重複訂單和平均訂單值
* **產品/內容檢視行為設定檔**：根據產品檢視次數和內容存取分析，透過行銷區段觸及潛在客戶
* 客戶也可以建立並排程&#x200B;**自訂再行銷區段**，以符合其使用者的需求。

## 整合必要條件{#integration-prerequisites}

說明成功整合的必要條件。

啟用此整合之前，請針對您的 Adobe Analytics 部署和電子郵件軟體審視下列項目。

這麼做可確保在啟動前已具備適當的最佳實務和必要條件，進而達成最佳的成功整合。

### Adobe Analytics 的必要條件 {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **報表套裝專用**：請注意，此整合供報表套裝專用。啟動整合之前，請確定已選取您所需的報表套裝
* **可用和已設定的 Analytics 變數**：此整合需要自訂事件和自訂 eVar，以及選用的其他事件和其他 eVar。

* **授權代表**：請注意，啟用此項整合可能會導致根據貴公司與 Adobe, Inc. 的服務協議或貴公司與 Adobe 信任合作夥伴的服務協議而產生費用，視適用情況而定。啟用這項整合，即表示您是貴公司的授權代表；因此，貴公司同意支付上述服務合約所載之費用 (若有的話)。
* **Adobe Analytics Data Warehouse**：此整合需要啟用 Adobe Analytics Data Warehouse，才能產生再行銷區段。如果您尚未啟用 Data Warehouse，請聯絡 Adobe 瞭解詳情。
* **收件者 ID**：此整合需要我們在 Analytics 變數 (eVar) 中擷取並儲存「訪客 ID」。訪客 ID (通常稱為「收件者 ID」) 是來自 Lyris 系統之電子郵件地址的編碼或數值表示法。此「收件者 ID」與網站上的下游訪客行為 (購物車放棄、購買等等) 相關聯此項目會被拉回 Lyris 系統，且可用於再行銷用途。作為設定程序的一部分，當精靈提示時，您必須識別用於此目的的 eVar 。
* **外部追蹤**：如果您目前沒有遵循針對所傳送每個電子郵件促銷活動啟用的外部追蹤最佳實務，您必須確實遵循，才能確保整合成功。如需詳細資訊，請參閱下文的 Lyris 一節
* **隱私權法規遵循**：您應瞭解，一旦啟用收件者或訪客 ID 追蹤功能，此功能便可追蹤您網站訪客的個人識別資訊。這隱含隱私疑慮，需要貴組織實施適當的程序，例如向網站訪客提供通知及取得其同意。

### Lyris EmailLabs 的必要條件 {#section-84abae9401224a3699fed861f715ebde}

* **有效的 Lyris 帳戶**：若要使用此 Data Connectors 整合，您必須擁有有效的 Lyris 帳戶。
* **帳戶資訊**：進行這項整合設定期間，您需要 Lyris 帳戶的下列相關資訊：

   * *Lyris API 金鑰*：用於資料填入
   * *查詢字串參數*：這些參數會附加在訊息 ID 和收件者 ID (訪客 ID) 的登陸頁面 URL 中。
   * *Lyris 伺服器/URL*：您在 Lyris 系統中使用的伺服器值
   * *Lyris 網站 ID*：也稱為「客戶 ID」，這是您 Lyris HQ 例項的不重複值。您可至 EmailLabs 「帳戶首頁」區域的「客戶資訊」下方取得此值。

## 為 Lyris 設定 Adobe Analytics 變數{#configure-adobe-analytics-variables-for-lyris}

說明要為每個報表套裝實施保留的 eVar 和事件。

此整合需要為每個報表套裝實施至少保留 2 個 eVar。除了這些 eVar 以外，還可能會保留一些事件，視您希望在 Analytics 中查看的 Lyris 資料而定。下表說明以下 eVar 和事件：

<table id="table_43E32344E9E54FED8491F28047249329"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數類型 </th> 
   <th colname="col2" class="entry"> 變數名稱 </th> 
   <th colname="col3" class="entry"> 變數的使用方式 </th> 
   <th colname="col4" class="entry"> 設定 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 訊息 ID </td> 
   <td colname="col3"> 擷取個別電子郵件訊息促銷活動身分識別 </td> 
   <td colname="col4"> <p>狀態：已啟用 </p> <p>配置：最近 </p> <p>到期時間：「業務決策」後 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 電子郵件收件者 ID </td> 
   <td colname="col3"> 擷取已點按電子郵件促銷活動之客戶的匿名身分識別 </td> 
   <td colname="col4"> <p>狀態：已啟用 </p> <p>配置：最近 </p> <p>到期時間：「業務決策」後 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 已傳送電子郵件數 </td> 
   <td colname="col3"> 儲存封 Lyris 所傳送的電子郵件數量 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 已開啟電子郵件數 </td> 
   <td colname="col3"> 儲存被開啟的電子郵件數量 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 不重複已開啟電子郵件數 </td> 
   <td colname="col3"> 儲存被開啟的不重複電子郵件數量 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 電子郵件點進次數 </td> 
   <td colname="col3"> 儲存任何電子郵件被點按的次數 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 電子郵件跳出數 </td> 
   <td colname="col3"> 儲存封跳出的電子郵件數量 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris - 電子郵件取消訂閱數 </td> 
   <td colname="col3"> 儲存封被停用的電子郵件訂閱數量 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
 </tbody> 
</table>
