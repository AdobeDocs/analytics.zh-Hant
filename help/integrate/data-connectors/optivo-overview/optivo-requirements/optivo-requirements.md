---
description: '啓動Data Connectors整合之前，請先完成下列需求 '
seo-description: '啓動Data Connectors整合之前，請先完成下列需求 '
seo-title: 啓動前
title: 啓動前
uuid: 45275635-a80 d-46c2-b9 ad-985df5737 fb2
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Before You Activate{#before-you-activate}

啓動Data Connectors整合之前，請先完成下列需求：

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **報表套裝特定：** 請注意，此整合是報告套裝特有的。在啓動整合之前，請確定您已選取所需的報表套裝。
* **可用且已設定的Adobe Analytics變數：** 此項整合需要自訂事件和自訂eVar。See [Adobe Analytics Integration Variables](../../optivo-overview/optivo-requirements/optivo-variables.md#concept-8ebd2bde4a1c4b0aad2987e050ffbbfc).

* **授權代表人：** 請注意，啓用此項整合可能會導致貴使用戶的公司根據您與Adobe，Inc或您與Adobe信任之合作夥伴之服務協議(如適用)，根據您的服務協議收取費用。啓動此整合表示您代表貴公司的授權代表；因此，貴使用戶同意支付上述服務協議所述之費用(如有的話)。
* **訊息ID：** 整合要求我們在Adobe Analytics變數(eVar)中擷取並儲存「訊息ID」。需要這些ID才能識別您傳送的郵件。在設定程序中，您必須在精靈提示時識別此用途的eVar。
* ** [!DNL ~Partner~]:** The integration requires that we capture and store a " [!DNL ~Partner~]" within a Adobe Analytics variable (eVar). This ID is an encoded or numeric representation of an email address from the [!DNL ~Partner~] system. This " [!DNL ~Partner~]" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled into the [!DNL ~Partner~] system and can be leveraged for remarketing purposes. 在設定程序中，您必須在精靈提示時識別此用途的eVar。
* **貼文點擊時間：** 在設定程序中，此整合需要指派給eVar的指派給符合貼文點擊動作時間的eVar。This is needed to transmit information about a recipient action to [!DNL ~Partner~] after the recipient clicked a link in a mailing.

* **貼文按一下產品：** 在設定程序中，此整合需要指派給與貼文點按動作相關聯之產品的eVar指派給eVar。This is needed to transmit information about a recipient action to [!DNL ~Partner~] after the recipient clicked a link in a mailing.

* **貼文點擊類型的動作：** 在設定程序中，此整合需要指派給eVar的指派給符合貼文點按動作類型的eVar。This is needed to transmit information about a recipient action to [!DNL ~Partner~] after the recipient clicked a link in a mailing.

* **隱私權合規性：** 您應瞭解，透過啓用「收件者ID」或「訪客ID追蹤」，此功能可追蹤網站訪客的個人識別資訊。這涉及隱私權方面的暗示，需要貴組織實作適當程序，例如向網站訪客發出通知並同意。

## Section Title {#section-370f12579a224d509545cba1c28adb22}

