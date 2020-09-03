---
description: 搭配Power BI使用Report Builder時的常見問題。
title: 疑難排解 Power BI 的整合問題
uuid: c1e7e164-4bc6-4513-9332-92c53be021cc
translation-type: tm+mt
source-git-commit: 3aae3b00db1d7f720641ed5ccbefd8acc03460e3
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 51%

---


# 疑難排解 Power BI 的整合問題

研究並解決搭配使用Power BI的報告建立工具時的常見問題。

## 無法發佈至 Power BI

需要發佈至 Power BI 的排程活頁簿仰賴 Power BI 服務來執行作業。無法發佈的兩大主因：

* Power BI 服務可能已停機。
* 將活頁簿排程的使用者已無有效的 Microsoft 帳戶憑證。

在每次排程執行時，每個 Report Builder 排程任務會嘗試執行三次。

* 第一次嘗試失敗後，您會看到這則訊息：「我們無法將此排程活頁簿發佈至 Microsoft Power BI。我們將稍後再試一次。」
* 第二次嘗試失敗後，您不會收到任何訊息。
* 第三次嘗試失敗後，您會看到這則訊息：「我們無法將此活頁簿發佈至 Power BI。」

## Power BI 中的視覺效果中斷

以下是將 Report Builder 請求發佈至 Power BI 後，視覺效果可能中斷的主要原因：

* 您在 Report Builder 中編輯請求，例如變更量度或維度，然後重新發佈至 Power BI。編輯請求可能會中斷視覺效果。
* 您刪除了視覺效果中使用的請求。

## 報告建立工具必須獲得授權才能存取您的組織資源。 此存取權只能由管理員授予。 要求管理員授予您權限。

請Microsoft管理員檢閱下方的「使用者可註冊應用程式」設定： **[!UICONTROL Microsoft Azure]** > **[!UICONTROL Azure Active Directory]** >使用者 **[!UICONTROL 設定允許選項]**。 如果此選項設為「否」，則該管理員可註冊這些類型的應用程式。

使用者可使用下列連結來授與存取 [權](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=logint&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US)。

管理員使用下列連結授予每個管理員的存 [取權](https://login.microsoftonline.com/common/oauth2/authorize?response_type=code&amp;prompt=admin_consent&amp;client_id=8d84f6d8-29a4-4484-a670-589b32400278&amp;redirect_uri=https%3a%2f%2fmy.omniture.com%2fsc15%2farb%2flogin.html&amp;resource=https%3a%2f%2fanalysis.windows.net%2fpowerbi%2fapi&amp;locale=en_US)。
