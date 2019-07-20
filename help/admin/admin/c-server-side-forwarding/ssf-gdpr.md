---
description: 'null'
seo-description: 'null'
seo-title: GDPR/E隱私權合規性與伺服器端轉送
title: GDPR/E隱私權合規性與伺服器端轉送
uuid: 1b90c567-3321-4dbd-a699-38c04 e809 fa4
translation-type: tm+mt
source-git-commit: 26c3cc9895c27d6abc452e0a4636771fb2415fb3

---


# GDPR/E隱私權合規性與伺服器端轉送

本節內容說明，根據[歐盟 Cookie 法規規範](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm) (已於 2017 年 9 月 30 日生效) 近期內推動之伺服器端轉送的增強功能。

Server-side forwarding is used to share data from Adobe Analytics to other [!DNL Experience Cloud Solutions], such as Audience Manager, in real time. 啟用伺服器端轉送功能後，可在資料收集程序期間期間，讓 Analytics 推送資料到其他 Experience Cloud 解決方案，以及讓這些解決方案推送資料到 Analytics。

直到最近，伺服器端轉送仍無法在同意與預先同意的事件/點擊間描述。自 2018 年 11 月 1 日起，您做為資料控管單位 (Adobe Analytics 客戶)，可選擇將預先同意的資料限制在 Adobe Analytics，並防止其轉送至 AAM。如此一來，實作環境變數有別於以往，可讓您標記未獲許可的點擊。設定變數時，可防止這些點擊在收到許可前傳送至 AAM。

When this new context variable, `cm.ssf=1`, exists on a hit, this hit gets flagged and does not get server-side-forwarded to AAM. 反之，若此字串並未出現在點擊，系統會將該點擊轉送至 AAM。

伺服器端轉送是雙向的，這代表當其適用於點擊，而系統將該點擊轉送至 AAM 時，Audience Analytics 會從 AAM 接收到該點擊的區段資訊，並將該資訊傳送回 Analytics。如此一來，任何非從 Analytics 伺服器端轉送至 AAM 的點擊，將不會加入 AAM 的 ID 區段清單。因此，將會存在不會從 AAM 取得區段 ID 資訊的流量/點擊子集。

## 實施詳細資料 {#section_FFA8B66085BF469FAB5365C944FE38F7}

請根據您的實施方法，遵循下列步驟。

| 實施方法 | 步驟 |
|--- |--- |
| Adobe Experience Platform Launch | Assuming you have the Adobe Analytics extension installed, add the following context data variable definition to the custom code editor within the Action configuration of a Rule: <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>Note:  Define the contextdata variable and set it to 1 if a customer does not consent to targeted marketing. Set the `contextdata` variable to *0* for customers who consented to targeted marketing. |
| DTM | 將內容變數定義新增至自訂頁面程式碼編輯器:<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注意: 若客戶不同意目標式行銷，請定義 contextData 變數，並將其設為「1」。對於同意目標式行銷的客戶，請將 contextData 變數設為「0」。 |
| AppMeasurement | 將內容資料變數定義新增至 AppMeasurement.js 檔案:<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注意: 若客戶不同意目標式行銷，請定義 contextData 變數，並將其設為「1」。對於同意目標式行銷的客戶，請將 contextData 變數設為「0」。 |

## 報表 (選用) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

您可以使用 Adobe Analytics 來報告，獲得同意且因此從伺服器端轉送的流量有多少，以及未獲得同意且未轉送至 AAM 的流量有多少。

若要設定此類型報表，請將新的內容變數，透過處理規則對應至自訂流量變數 (prop)。若要這麼做

1. 請實施「cm.ssf」變數 (如上所示)。
1. [啟用 prop。](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. 使用處理規則將內容變數對應至 prop。

   1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** , then select a report suite.
   1. Click  **[!UICONTROL Edit Report Suite]** &gt; **[!UICONTROL General]** &gt; **[!UICONTROL Processing Rules]** .
   1. 按一下&#x200B;**[!UICONTROL 「新增規則」。」]**
   1. Under **[!UICONTROL Always Execute]**, overwrite the value of the prop you had enabled with the context variable “cm.ssf(Context Data)”.
   1. 按一下&#x200B;**[!UICONTROL 儲存]**。

