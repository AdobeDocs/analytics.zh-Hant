---
description: 搭配 Power BI 使用 Report Builder 時的常見問題。
title: 疑難排解 Power BI 的整合問題
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
TQID: https://experienceleague.adobe.com/Q4n08pGcqBwhUl5q3VnWhuVcW9E-tdvv3LoHSLoGleA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 382
ht-degree: 46%

---

# 疑難排解 Power BI 的整合問題

{{legacy-arb}}

研究並解決搭配 Power BI 使用 Report Builder 時的常見問題。

## 無法發佈至 Power BI

需要Power BI發佈的已排程活頁簿取決於Power BI服務是否正常運作。 無法發佈的兩大主因：

* Power BI服務可能已關閉。
* 排程活頁簿的使用者不再具備有效的Microsoft帳戶認證。

每個Report Builder排程工作會在每次排程執行時嘗試三次：

* 第一次嘗試失敗後，您會看到這則訊息：「我們無法將此排程活頁簿發佈至 Microsoft Power BI。 我們很快將再試一次。」
* 第二次嘗試失敗後，您將不會收到任何訊息。
* 第三次嘗試失敗後，您會看到這則訊息：「我們無法將此活頁簿發佈至 Power BI。」

## Power BI 中的視覺效果遭到破壞

以下是將 Report Builder 請求發佈至 Power BI 後，視覺效果可能中斷的主要原因：

* 您編輯了Report Builder中的請求（例如變更量度或維度），然後重新發佈至Power BI。 編輯請求可能會破壞您的視覺效果。
* 您已刪除用於視覺效果的要求。

>[!IMPORTANT]
>
>Report Builder需要管理員來授權存取您的組織資源。 如果您需要存取權，請要求管理員授與您許可權。
> Microsoft管理員可以檢閱&#x200B;*使用者可以註冊應用程式*&#x200B;設定，該設定可在&#x200B;**[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL 使用者設定允許選項]**&#x200B;下找到。 如果此選項設定為&#x200B;**否**，則管理員可以註冊這些型別的應用程式。

使用者可登入其[Microsoft Power BI帳戶](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=logint&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US)，藉此授與存取權。

管理員可以登入[管理員的Microsoft Power BI帳戶](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&prompt=admin_consent&client_id=8d84f6d8-29a4-4484-a670-589b32400278&redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&locale=en_US)，授與存取權給所有人。

## 達到API限制

Power BI中的報表可與Analytics報表API搭配使用，因此適用API臨界值限制。
