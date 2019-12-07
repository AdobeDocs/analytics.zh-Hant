---
description: 'null'
title: Adobe Analytics的Selligent Data Connector
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Selligent Data Connector for Adobe Analytics{#selligent-data-connector-for-adobe-analytics}

此整合包含下列主要優點：

* 將電子郵件行銷與分析資料整合至單一報告介面。
* 透過轉化和對收入和網站成功的貢獻，最佳化電子郵件宣傳。
* 根據動態行銷區隔，重新行銷至關鍵訪客和市場區隔。

## 動態行銷區段 {#section-a2216f3339304636bd5417249bd635a4}

此電子郵件整合支援動態行銷細分，以協助您推動業務發展。 此整合具備下列立即可用的行銷區段：

| 區段 | 說明 |
|---|---|
| **購物車放棄設定檔** | 透過專為猶豫是否要完成購物車的訪客量身打造的微調促銷活動，協助訪客轉化為客戶。 |
| **購買設定檔** | 透過訪客購買模式所定位的促銷活動，增加重複訂單和平均訂單值。 |
| **產品／內容檢視行為設定檔** | 根據產品檢視和內容存取分析，透過行銷細分觸及潛在客戶。 |
| **自訂重新行銷區段** | 客戶也可以根據其使用者的需求建立並排程自訂的再行銷區段。 |

## 啟動此整合前{#before-you-activate-this-integration}

在啟動此整合之前，請針對您部署的Adobe Analytics和電子郵件軟體檢視下列項目。

如此可確保在啟動前已有適當的最佳實務和先決條件。 這將帶來最佳且成功的整合。

## Adobe Analytics的必要條件{#prerequisites-for-adobe-analytics}

列出在部署整合之前，在Adobe Analytics中要採取的必要動作。

| 先決條件 | 附註 |
|---|---|
| 選取報表套裝 | 請注意，此整合是報表套裝專用的。 在啟動整合之前，請確定您已選取所需的報表套裝。 |
| 設定Analytics變數 | 此整合需要自訂事件和自訂eVar，以及選擇性的其他事件和其他eVar。 請參閱設定Analytics變數以供Selligent使用。 |
| 授權代表 | 請注意，啟用此項整合可能會使貴公司根據您與Adobe, Inc.的服務合約或您與Adobe信任的合作夥伴之一（視情況而定）的服務合約產生費用。 啟動此整合後，您即表示您是您公司的授權代表；因此，貴公司同意支付上述服務協定所載之費用（如有）。 |
| 啟用Adobe Data Warehouse™ | 此整合需要啟用「資料倉庫」才能產生再行銷區段。 如果您尚未啟用Adobe資料倉庫，請聯絡Adobe以取得詳細資訊。 |
| Recipient ID | 整合需要我們擷取並儲存Analytics變數(eVar)中的「訪客ID」。 訪客ID（通常稱為「收件者ID」）是來自Selligent系統之電子郵件地址的編碼或數值表示法。 此「收件者ID」與網站上的下游訪客行為（購物車放棄、購買等）相關聯這些資料會被拉回Selligent系統，並可用於再行銷用途。 在設定程式中，當精靈提示時，您必須識別eVar以用於此目的。 |
| 外部追蹤 | 如果您目前未遵循針對您傳送的每個電子郵件促銷活動啟用外部追蹤的最佳實務，您必須這麼做，以確保成功整合。 如需詳細資訊，請參閱下方的「選擇」區段。 |
| 隱私權規範 | 您應瞭解，透過啟用「收件者」或「訪客ID」追蹤，此功能可追蹤您網站訪客的個人識別資訊。 這涉及隱私權問題，需要貴組織實施適當的程式，例如向網站訪客提供通知並給予同意。 |

## 設定Selligent的Analytics變數{#configure-analytics-variables-for-selligent}

此整合需要為每個報表套裝實作保留2個eVar。

除了這些eVar以外，您可能會根據Selligent中的資料保留一些事件，您想在Analytics中看到這些資料。 這些eVar和事件說明如下：

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數類型 </th> 
   <th colname="col2" class="entry"> 變數名稱 </th> 
   <th colname="col3" class="entry"> 如何使用 </th> 
   <th colname="col4" class="entry"> 設定 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 訊息ID </td> 
   <td colname="col3"> 若要擷取個別電子郵件訊息促銷活動識別碼。 </td> 
   <td colname="col4"> <p><b>狀態</b>:已啟用 </p> <p><b>配置</b>:最近 </p> <p><b>過期時間</b>:「業務決策」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eV ar </td> 
   <td colname="col2"> Recipient ID </td> 
   <td colname="col3"> 若要擷取點按電子郵件促銷活動之客戶的匿名身分識別。 </td> 
   <td colname="col4"> <p><b>狀態</b>:已啟用 </p> <p><b>配置</b>:最近 </p> <p><b>過期時間</b>:「業務決策」 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 已傳送 </td> 
   <td colname="col3"> 儲存從Selligent傳送的電子郵件數。 </td> 
   <td colname="col4"> <p><b>類型</b>:數值 </p> <p><b>參與率</b>:已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 交付 </td> 
   <td colname="col3"> 儲存傳送的電子郵件數。 </td> 
   <td colname="col4"> <p><b>類型</b>:數值 </p> <p><b>參與率</b>:已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 檢視 </td> 
   <td colname="col3"> 儲存已檢視的獨特電子郵件數。 </td> 
   <td colname="col4"> <p><b>類型</b>:數值 </p> <p><b>參與率</b>:已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 點擊次數 </td> 
   <td colname="col3"> 儲存任何電子郵件被點按的次數。 </td> 
   <td colname="col4"> <p><b>類型</b>:數值 </p> <p><b>參與率</b>:已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 事件 </td> 
   <td colname="col2"> 已反彈 </td> 
   <td colname="col3"> 儲存遭拒收的電子郵件數量。 </td> 
   <td colname="col4"> <p><b>類型</b>:數值 </p> <p><b>參與率</b>:已啟用 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Selligent的先決條件{#prerequisites-for-selligent}

列出在部署整合之前，從您的Selligent帳戶提供的必要資訊。

**有效的Selligent帳戶**

若要使用此「資料連接器」整合，您必須擁有有效的Selligent帳戶。

**帳戶資訊**

在此整合設定期間，您會要求您提供下列Selligent帳戶的相關資訊：

* **Adobe服務URL**:

   URL可從用來登入Selligent Marketing解決方案的URL衍生。 將URL的「/simweb/login.aspx」部分取代為「/automation/omniture.asmx」

   E.g: `http://<client-specific install url>/automation/omniture.asmx`

* **** 查詢字串參數：這些會附加在「訊息ID」和「收件者ID」（訪客ID）的著陸頁面URL中。 郵件ID和收件者ID一律為MID和RID。

* **Integration Token** 從Simweb內啟動Manager工具，然後前往 **[!UICONTROL Configuration]** &gt; **[!UICONTROL System Settings]** &gt; General **[!UICONTROL （整合令牌）&gt;]****** System System標籤頁。 在「 **[!UICONTROL 安全性]**」下方，您可以找到整合Token。

   ![](assets/selligent-integration_token.png)
