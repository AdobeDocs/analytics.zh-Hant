---
description: 說明透過整合所實現的行銷效率。
title: Adobe Analytics的Lyris Data Connector
uuid: db213865-1296-4a93-a0a2-781c026b2be5
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Lyris Data Connector for Adobe Analytics{#lyris-data-connector-for-adobe-analytics}

說明透過整合所實現的行銷效率。

Adobe® Data Connectors™電子郵件整合將Adobe Analytics的行為資訊與Lyris電子郵件行銷相結合，重新定義成功評估並透過更相關的訊息鎖定受眾。

向這些市場細分傳遞相關電子郵件訊息可帶來全新的營收商機，進而推動新電子郵件和現有電子郵件宣傳的轉化率和營收。 例如，根據瀏覽期間檢視的產品或放棄購物車中的產品，傳送相關的電子郵件訊息已證明對收入有顯著影響，而且對成本的影響最小，因為這只是利用您網站已獲取的訪客。

這種行銷效率的提升，是整合Adobe Analytics與Lyris的主要優點之一。 此外，此整合將自動將電子郵件量度與Adobe Analytics資料同步化，與閉環報告的每小時同步頻率相同。

## 主要優點和功能{#key-benefits-and-features}

說明整合Lyris和Adobe行銷報告與分析的主要優點。

Lyris與Adobe Analytics的整合提供下列主要優點：

* 將電子郵件行銷與分析資料整合至單一報告介面
* 透過轉化和對收入和網站成功的貢獻，最佳化電子郵件宣傳
* 根據動態行銷區隔，重新行銷關鍵訪客和市場區隔

### 動態行銷區段

電子郵件整合支援動態行銷細分，以協助您推動業務發展。 此整合具備下列立即可用的行銷區段：

* **購物車放棄設定檔**:透過專為猶豫是否要完成購物車的訪客量身打造的微調促銷活動，協助訪客轉化為客戶
* **購買設定檔**:透過訪客購買模式所定位的促銷活動，增加重複訂單和平均訂單值
* **產品／內容檢視行為設定檔**:根據產品檢視和內容存取分析，透過行銷細分觸及潛在客戶
* 客戶也可以建立並排 **程自訂的再行銷區段** ，以符合其使用者的需求。

## 整合必要條件{#integration-prerequisites}

說明成功整合的先決條件。

在啟動此整合之前，請針對您部署的Adobe Analytics和電子郵件軟體檢視下列項目。

如此可確保在啟動前已有適當的最佳實務和先決條件，進而產生最佳且成功的整合。

### Adobe Analytics的必要條件 {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **報表套裝專用**:請注意，此整合是報表套裝專用的。 在啟動整合之前，請確定您已選取所需的報表套裝
* **可用和設定的Analytics變數**:此整合需要自訂事件和自訂eVar，以及選擇性的其他事件和其他eVar。

* **授權代表**:請注意，啟用此項整合可能會使貴公司根據您與Adobe, Inc.的服務合約或您與Adobe信任的合作夥伴之一（視情況而定）的服務合約產生費用。 啟動此整合後，您即表示您是您公司的授權代表；因此，貴公司同意支付上述服務協定所載之費用（如有）。
* **Adobe Analytics資料倉庫**:此整合需要啟用Adobe Analytics資料倉庫，才能產生再行銷區段。 如果您尚未啟用資料倉庫，請聯絡Adobe以取得詳細資訊。
* **收件者ID**:整合需要我們擷取並儲存Analytics變數(eVar)中的「訪客ID」。 訪客ID（通常稱為「收件者ID」）是來自Lyris系統之電子郵件地址的編碼或數值表示法。 此「收件者ID」與網站上的下游訪客行為（購物車放棄、購買等）相關聯這些資產被拉回Lyris系統，並可用於再行銷目的。 在設定程式中，當精靈提示時，您必須識別eVar以用於此目的。
* **外部追蹤**:如果您目前未遵循為所傳送的每個電子郵件促銷活動啟用外部追蹤的最佳實務，您必須這麼做，以確保成功整合。 如需詳細資訊，請參閱下方的Lyris章節
* **隱私權規範**:您應瞭解，透過啟用「收件者」或「訪客ID」追蹤，此功能可追蹤您網站訪客的個人識別資訊。 這會影響隱私權，需要貴組織實施適當的程式，例如向網站訪客提供通知並給予同意。

### Lyris emailLabs的先決條件 {#section-84abae9401224a3699fed861f715ebde}

* **有效的Lyris帳戶**:若要使用此資料連接器整合，您必須擁有有效的Lyris帳戶。
* **帳戶資訊**:在此整合設定期間，您需要下列有關Lyris帳戶的資訊：

   * *Lyris API金鑰*:用於資料填入
   * *查詢字串參數*:這些會附加在「訊息ID」和「收件者ID」（訪客ID）的著陸頁面URL中。
   * *Lyris Server/URL*:您在Lyris系統中使用的伺服器值
   * *Lyris網站ID*:這也稱為「客戶ID」，是您Lyris HQ例項的唯一值。 這可以位於EmailLabs的「Account Home」（帳戶首頁）部分的「Customer Info」（客戶資訊）下。

## 為Lyris設定Adobe Analytics變數{#configure-adobe-analytics-variables-for-lyris}

說明要為每個報表套裝實施保留的eVar和事件。

此整合需要為每個報表套裝實作至少保留2個eVar。 除了這些eVar以外，可能會保留一些事件，視您要在Analytics中查看的Lyris資料而定。 下表說明這些eVar和事件：

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
   <td colname="col2"> 訊息ID </td> 
   <td colname="col3"> 若要擷取個別電子郵件訊息促銷活動識別 </td> 
   <td colname="col4"> <p>狀態：已啟用 </p> <p>配置：最近 </p> <p>過期時間：「業務決策」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> Email Recipient ID </td> 
   <td colname="col3"> 若要擷取您客戶的匿名身分識別，而您的客戶已點選電子郵件促銷活動 </td> 
   <td colname="col4"> <p>狀態：已啟用 </p> <p>配置：最近 </p> <p>過期時間：「業務決策」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 傳送的電子郵件 </td> 
   <td colname="col3"> 儲存號。 利里斯寄來的電子郵件 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 開啟的電子郵件 </td> 
   <td colname="col3"> 儲存號。 開啟的電子郵件 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 開啟的獨特電子郵件 </td> 
   <td colname="col3"> 儲存號。 開啟的獨特電子郵件 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 電子郵件點進次數 </td> 
   <td colname="col3"> 儲存號。 點擊任何電子郵件的次數 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 電子郵件彈回數 </td> 
   <td colname="col3"> 來儲存號碼。 被拒收的郵件 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> Lyris —— 電子郵件取消訂閱 </td> 
   <td colname="col3"> 來儲存號碼。 已停用的電子郵件訂閱 </td> 
   <td colname="col4">類型：數值 <p>參與率：已啟用 </p> </td> 
  </tr> 
 </tbody> 
</table>
