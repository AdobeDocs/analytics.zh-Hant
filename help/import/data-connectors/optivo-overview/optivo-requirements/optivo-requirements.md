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
source-git-commit: e96de98b3176a05654fdf697210f992b0fd4adb1

---


# 啓動前{#before-you-activate}

啓動Data Connectors整合之前，請先完成下列需求：

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **報表套裝特定：** 請注意，此整合是報告套裝特有的。在啓動整合之前，請確定您已選取所需的報表套裝。
* **可用且已設定的Adobe Analytics變數：** 此項整合需要自訂事件和自訂eVar。請參閱 [Adobe Analytics整合變數](../../optivo-overview/optivo-requirements/optivo-variables.md#concept-8ebd2bde4a1c4b0aad2987e050ffbbfc)。

* **授權代表人：** 請注意，啓用此項整合可能會導致貴使用戶的公司根據您與Adobe，Inc或您與Adobe信任之合作夥伴之服務協議(如適用)，根據您的服務協議收取費用。啓動此整合表示您代表貴公司的授權代表；因此，貴使用戶同意支付上述服務協議所述之費用(如有的話)。
* **訊息ID：** 整合要求我們在Adobe Analytics變數(eVar)中擷取並儲存「訊息ID」。需要這些ID才能識別您傳送的郵件。在設定程序中，您必須在精靈提示時識別此用途的eVar。
* ** [!DNL ~合作夥伴~]：**整合要求我們在Adobe Analytics變數(eVar)中擷取並儲存「 [!DNL ~合作夥伴~]」。此ID是 [!DNL ~來自合作夥伴~] 系統的電子郵件地址編碼或數值表示。此「 [!DNL ~合作夥伴~]」與網站上下游訪客行為(購物車放棄、購買等)關聯被提取到 [!DNL ~合作夥伴~] 系統中，並可利用以進行再行銷。在設定程序中，您必須在精靈提示時識別此用途的eVar。
* **貼文點擊時間：** 在設定程序中，此整合需要指派給eVar的指派給符合貼文點擊動作時間的eVar。當收件者按一下郵件中的連結後 [!DNL ~，~] 就需要將收件者動作的相關資訊傳送給合作夥伴。

* **貼文按一下產品：** 在設定程序中，此整合需要指派給與貼文點按動作相關聯之產品的eVar指派給eVar。當收件者按一下郵件中的連結後 [!DNL ~，~] 就需要將收件者動作的相關資訊傳送給合作夥伴。

* **貼文點擊類型的動作：** 在設定程序中，此整合需要指派給eVar的指派給符合貼文點按動作類型的eVar。當收件者按一下郵件中的連結後 [!DNL ~，~] 就需要將收件者動作的相關資訊傳送給合作夥伴。

* **隱私權合規性：** 您應瞭解，透過啓用「收件者ID」或「訪客ID追蹤」，此功能可追蹤網站訪客的個人識別資訊。這涉及隱私權方面的暗示，需要貴組織實作適當程序，例如向網站訪客發出通知並同意。

## 章節標題 {#section-370f12579a224d509545cba1c28adb22}

