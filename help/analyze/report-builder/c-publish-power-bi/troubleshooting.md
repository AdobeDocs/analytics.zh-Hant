---
description: 搭配 Power BI 使用 Report Builder 時的常見問題。
title: 疑難排解 Power BI 的整合問題
feature: Report Builder
role: User, Admin
exl-id: adb13a0e-99fb-48f5-add2-204d155e467f
source-git-commit: f6f65f34c4d8caf04eb3ea47108e36e5b9adf24f
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 89%

---

# 疑難排解 Power BI 的整合問題

研究並解決搭配 Power BI 使用 Report Builder 時的常見問題。

## 無法發佈至 Power BI

需要發佈至 Power BI 的排程活頁簿仰賴 Power BI 服務來執行作業。無法發佈的兩大主因：

* Power BI 服務可能已停機。
* 將活頁簿排程的使用者已無有效的 Microsoft 帳戶憑證。

在每次排程執行時，每個 Report Builder 排程任務會嘗試執行三次。

* 第一次嘗試失敗後，您會看到這則訊息：「我們無法將此排程活頁簿發佈至 Microsoft Power BI。我們將稍後再試一次。」
* 第二次嘗試失敗後，您不會收到任何訊息。
* 第三次嘗試失敗後，您會看到這則訊息：「我們無法將此活頁簿發佈至 Power BI。」

## Power BI 中的視覺效果遭到破壞

以下是將 Report Builder 請求發佈至 Power BI 後，視覺效果可能中斷的主要原因：

* 您在 Report Builder 中編輯請求，例如變更量度或維度，然後重新發佈至 Power BI。編輯請求可能會中斷視覺效果。
* 您刪除了視覺效果中使用的請求。

## Report Builder 需要被授權才能存取貴組織的資源。 只有管理員可以授與這項存取權。 請要求管理員授與您權限。

請 Microsoft 管理員檢閱以下位置底下的「使用者可以註冊應用程式」設定：**[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** > **[!UICONTROL 使用者設定允許選項]**。 如果此選項設定為「否」，則表示管理員可以註冊這些類型的應用程式。

使用者可以使用以下[連結](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US)授與存取權。

管理員使用以下[連結](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US)授與存取權給所有人。

## 達到API限制

在Power BI中建立報表可與Analytics報表API搭配使用，因此會套用API臨界值限制。 如需詳細資訊，請參閱 [網站服務錯誤代碼](https://github.com/AdobeDocs/analytics-1.4-apis/blob/3dda746890743c2098256719d6595109b7748262/docs/getting-started/c_Web_Services_Error_Codes.md).
