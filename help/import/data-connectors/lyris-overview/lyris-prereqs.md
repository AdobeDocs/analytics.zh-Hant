---
description: 說明成功整合的必要條件。
seo-description: 說明成功整合的必要條件。
seo-title: 整合必要條件
solution: Analytics
title: 整合必要條件
uuid: ac93fb4d-a07-1fac-3d42-c4856463 cbb6
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 整合必要條件{#integration-prerequisites}

說明成功整合的必要條件。

在啓動此整合之前，請先檢視下列項目，以免您部署Adobe Analytics和您的電子郵件軟體。

如此可確保在啓動前提供適當的最佳實務和預先要求，進而實現最佳且成功的整合。

## Adobe Analytics的必要條件 {#section-ddb9d4f3b283438ea33788f47f35e69a}

* **報表套裝特定**：請注意，此整合與報表套裝特定。在啓動整合之前，確定您已選取所需的報表套裝
* **可用且已設定的Analytics變數**：此項整合需要自訂事件和自訂eVar，以及選擇性的其他事件和其他eVar。

   請參閱 [設定Lynris的Analytics變數](../lyris-overview/lyris-analytics-variables.md#task-e70a62dc096d4f548d5070a67822f5e7)

* **授權代表人**：請注意，啓用此項整合可能會導致貴使用戶的公司根據您與Adobe，Inc或您與Adobe信任之合作夥伴之服務協議(如適用)，根據您的服務協議收取費用。啓動此整合表示您代表貴公司的授權代表；因此，貴使用戶同意支付上述服務協議所述之費用(如有的話)。
* **Adobe Analytics資料倉庫**：這項整合需要啓用Adobe Analytics資料倉庫，才能產生重新行銷區段。如果您尚未啓用資料倉庫，請聯絡Adobe以取得詳細資訊。
* **收件者ID**：整合要求我們在Analytics變數(eVar)中擷取並儲存「訪客ID」。訪客ID(通常稱為「收件者ID」)是由Lyris系統的電子郵件地址編碼或數值表示。此「收件者ID」與網站上下游訪客行為(購物車放棄、購買等)關聯它會被提取到Lyris系統中，並可運用於重新行銷用途。在設定程序中，您必須在精靈提示時識別此用途的eVar。
* **外部追蹤**：如果您目前尚未針對您傳送的每個電子郵件促銷活動啓用外部追蹤，則必須這樣做以確保整合成功。請參閱下面的Lynris章節以取得詳細資訊
* **隱私權合規性**：您應瞭解，透過啓用「收件者ID」或「訪客ID追蹤」，此功能可追蹤網站訪客的個人識別資訊。這對隱私權造成影響，要求貴組織實作適當程序，例如向網站訪客提供通知並同意。

## Lynris EmailLabs的必要條件 {#section-84abae9401224a3699fed861f715ebde}

* **有效的Lyris帳戶**：若要使用此資料連接器整合，您必須擁有有效的Lyris帳戶。
* **帳戶資訊**：在此整合設定期間，您將需要有關您Lyris帳戶的下列資訊：

   * *Lynris API金鑰*：用於資料族群
   * *查詢字串參數*：這些項目會附加在訊息ID和收件者ID的著陸頁面URL(訪客ID)中。
   * *Lyris Server/URL*：您在Lynris系統中使用的伺服器值
   * *Lyris網站ID*：這也稱為「客戶ID」，這是您Lynris HQ例項的唯一值。This can be located under「Customer Info」of the「Account Home」一節of eAmailLabs.

