---
description: 'null'
title: Adobe Analytics 的 Selligent Data Connector
uuid: e16c3ca6-b131-44b1-a36c-e39697677a96
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Adobe Analytics 的 Selligent Data Connector{#selligent-data-connector-for-adobe-analytics}

這項整合包含下列主要優點：

* 將電子郵件行銷與分析資料整合至單一報表介面。
* 透過轉換和對收入和網站成功的貢獻，最佳化電子郵件促銷活動。
* 根據動態行銷區段，再行銷關鍵訪客和市場區塊。

## 動態行銷區段 {#section-a2216f3339304636bd5417249bd635a4}

此電子郵件整合支援動態行銷區段，可協助您推動業務發展。這項整合具備下列立即可用的行銷區段：

| 區段 | 說明 |
|---|---|
| **放棄購買設定檔** | 透過專為猶豫是否要完成購買購物車項目的訪客量身打造的微調促銷活動，協助將訪客轉化為客戶。 |
| **購買設定檔** | 透過鎖定訪客購買模式為目標的促銷活動，增加重複訂單和平均訂單值。 |
| **產品/內容檢視行為設定檔** | 根據產品檢視次數和內容存取分析，透過行銷區段觸及潛在客戶。 |
| **自訂再行銷區段** | 客戶也可以建立並排程自訂再行銷區段，以符合其使用者的需求。 |

## 啟用這項整合的事前準備{#before-you-activate-this-integration}

在啟用這項整合之前，請針對您部署的 Adobe Analytics 和您的電子郵件軟體檢閱下列項目。

這麼做將可確保在啟動前已具備適當的最佳實務和必要條件，進而達成最佳的成功整合。

## Adobe Analytics 的必要條件{#prerequisites-for-adobe-analytics}

列出部署整合之前，需在 Adobe Analytics 中要採取的必要動作。

| 先決條件 | 附註 |
|---|---|
| 選取報表套裝 | 請注意，此整合供報表套裝專用。在啟用整合之前，請確定您已選取所需的報表套裝。 |
| 設定 Analytics 變數 | 此整合需要自訂事件和自訂 eVar，以及選用的其他事件和其他 eVar。請參閱「設定 Analytics 變數以供 Selligent 使用」。 |
| 授權代表 | 請注意，啟用此項整合可能會使貴公司根據您與 Adobe, Inc. 的服務合約或您與 Adobe 信任的合作夥伴之一 (如適用) 的服務合約產生費用。啟用這項整合，即表示您是貴公司的授權代表；因此，貴公司同意支付上述服務合約所載之費用 (若有的話)。 |
| 啟用 Adobe Data Warehouse™ | 此整合需要啟用 Data Warehouse，才能產生再行銷區段。如果您尚未啟用 Adobe Data Warehouse，請聯絡 Adobe 瞭解詳情。 |
| 收件者 ID | 此整合需要我們在 Analytics 變數 (eVar) 中擷取並儲存「訪客 ID」。訪客 ID (通常稱為「收件者 ID」) 是來自 Selligent 系統之電子郵件地址的編碼或數值表示法。此「收件者 ID」與網站上的下游訪客行為 (購物車放棄、購買等等) 相關聯此項目會被拉回 Selligent 系統，且可用於再行銷用途。作為設定程序的一部分，當精靈提示時，您必須識別用於此目的的 eVar 。 |
| 外部追蹤 | 如果您目前沒有遵循針對所傳送每個電子郵件促銷活動啟用的外部追蹤最佳實務，您必須確實遵循，才能確保整合成功。如需詳細資訊，請參閱下文的 Selligent 一節。 |
| 隱私權法規遵循 | 您應瞭解，一旦啟用收件者或訪客 ID 追蹤功能，此功能便可追蹤您網站訪客的個人識別資訊。這隱含隱私權問題，需要您的組織實施適當的程序，例如向您的網站訪客提供通知並授予同意。 |

## 設定 Analytics 變數以供 Selligent 使用{#configure-analytics-variables-for-selligent}

此整合需要為每個報表套裝實施保留 2 個 eVar。

除了這些 eVar 以外，還可能會保留一些事件，視您希望在 Analytics 中查看的 Selligent 資料而定。下表說明這些 eVar 和事件：

<table id="table_2FFB865DBD80412F90DA8E224B12FB62"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 變數類型 </th> 
   <th colname="col2" class="entry"> 變數名稱 </th> 
   <th colname="col3" class="entry"> 使用方式 </th> 
   <th colname="col4" class="entry"> 設定 </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 訊息 ID </td> 
   <td colname="col3"> 擷取個別電子郵件訊息促銷活動身分識別。 </td> 
   <td colname="col4"> <p><b>狀態</b>：已啟用 </p> <p><b>配置</b>：最近 </p> <p><b>到期時間</b>：「業務決策」後 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> eVar </td> 
   <td colname="col2"> 收件者 ID </td> 
   <td colname="col3"> 擷取已點按電子郵件促銷活動之客戶的匿名身分識別。 </td> 
   <td colname="col4"> <p><b>狀態</b>：已啟用 </p> <p><b>配置</b>：最近 </p> <p><b>到期時間</b>：「業務決策」後 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> 已傳送 </td> 
   <td colname="col3"> 儲存從 Selligent 傳送的電子郵件數量。 </td> 
   <td colname="col4"> <p><b>類型</b>：數值 </p> <p><b>參與率</b>：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> 已傳遞 </td> 
   <td colname="col3"> 儲存已遞送的電子郵件數量。 </td> 
   <td colname="col4"> <p><b>類型</b>：數值 </p> <p><b>參與率</b>：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> 檢視 </td> 
   <td colname="col3"> 儲存被檢視的不重複電子郵件數量。 </td> 
   <td colname="col4"> <p><b>類型</b>：數值 </p> <p><b>參與率</b>：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> 點擊次數 </td> 
   <td colname="col3"> 儲存任何電子郵件被點按的次數。 </td> 
   <td colname="col4"> <p><b>類型</b>：數值 </p> <p><b>參與率</b>：已啟用 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Event </td> 
   <td colname="col2"> 已跳出 </td> 
   <td colname="col3"> 儲存跳出的電子郵件數量。 </td> 
   <td colname="col4"> <p><b>類型</b>：數值 </p> <p><b>參與率</b>：已啟用 </p> </td> 
  </tr> 
 </tbody> 
</table>

## Selligent 的必備條件{#prerequisites-for-selligent}

列出部署整合之前，從您的 Selligent 帳戶提供的必要資訊。

**有效的 Selligent 帳戶**

若要使用此 Data Connectors 整合，您必須具備有效的 Selligent 帳戶。

**帳戶資訊**

進行這項整合設定期間，您需要 Selligent 帳戶的下列相關資訊：

* **Adobe 服務 URL**：

   此 URL 可從用來登入 Selligent Marketing 解決方案的 URL 衍生。將 URL 的「/simweb/login.aspx」部分取代為「/automation/omniture.asmx」

   例如：`http://<client-specific install url>/automation/omniture.asmx`

* **查詢字串參數：**&#x200B;這些參數會附加在訊息 ID 和收件者 ID (訪客 ID) 的登陸頁面 URL 中。訊息 ID 和收件者 ID 一律為 MID 和 RID。

* **整合代號** 從 Simweb 內啟動管理器工具，然後前往&#x200B;**[!UICONTROL 「設定]** > **[!UICONTROL 系統設定]** > **[!UICONTROL 一般]**&#x200B;標籤 >**[!UICONTROL 系統」]**。您可以在&#x200B;**[!UICONTROL 安全性]**&#x200B;下方找到整合代號。

   ![](assets/selligent-integration_token.png)
