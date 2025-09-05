---
description: 解釋由歐盟 Cookie 合規性法規推動的伺服器端轉送的增強功能。
title: GDPR/ePrivacy 法規遵循與伺服器端轉送
feature: Report Suite Settings
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
role: Admin
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 55%

---

# GDPR/ePrivacy 法規遵循與伺服器端轉送

本節內容將解釋[歐盟 Cookie 合規性法規](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+and+similar+technologies) (已於 2017 年 9 月 30 日生效) 推動之伺服器端轉送的增強功能。

伺服器端轉送可用於即時將資料從 Adobe Analytics 分享至其他 [!DNL Experience Cloud Solutions] (例如 Audience Manager)。啟用伺服器端轉送功能後，也可在資料收集過程中讓 Analytics 推送資料到其他 Experience Cloud 解決方案，並讓這些解決方案推送資料到 Analytics。

在過去，伺服器端轉送無法區分同意與預先同意的事件/點擊。 自2018年11月1日起，您做為資料控管單位(Adobe Analytics客戶)可以選擇將預先許可的資料限制在Adobe Analytics，並防止其轉送至Adobe Audience Manager。 新的實作內容變數可讓您在未收到同意的地方標籤點擊。 變數一經設定，在收到同意之前不會將這些點選傳送至Adobe Audience Manager。

這個新的內容變數`cm.ssf=1`存在於點選時，系統會標籤該點選，且不會將其從伺服器端轉送至Adobe Audience Manager。 相反地，如果此字串未出現在點選上，則點選會轉送至Adobe Audience Manager。

伺服器端轉送是雙向的，這表示當點選套用至點選，且該點選轉送至Adobe Audience Manager時，Audience Analytics會從Adobe Audience Manager接收該點選的區段資訊，並將其傳回Analytics。 因此，任何非伺服器端轉送自Analytics至Adobe Audience Manager的點選，都不會富含Adobe Audience Manager的區段ID清單。 因此，將有流量/點選的子集，不會從Adobe Audience Manager取得區段ID資訊。

## 實作詳細資料 {#section_FFA8B66085BF469FAB5365C944FE38F7}

請根據您的實作方法，遵循下列步驟。

| 實作方法 | 步驟 |
|--- |--- |
| Adobe Experience Platform 中的標記 | 假設您已安裝 Adobe Analytics 擴充功能，請在「規則」的「動作」設定中，將下方的內容資料變數定義加到自訂程式碼編輯器：<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>注意：若客戶不同意目標式行銷，請定義 contextdata 變數，並將其設為「1」。 如果客戶同意目標式行銷，請將 `contextdata` 變數設為 *0*。 |
| AppMeasurement | 將內容資料變數定義新增至AppMeasurement.js檔案： <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>注意：若客戶不同意目標式行銷，請定義contextdata變數，並將其設為「1」。 對於同意目標式行銷的客戶，請將 contextData 變數設為「0」。 |

## 報告 (選用) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

您可以使用Adobe Analytics來報告有多少流量是經過同意且由伺服器端轉送，以及有多少流量不是經過同意且尚未轉送至Adobe Audience Manager。

若要設定此類型報表，請將新的內容變數，透過處理規則對應至自訂流量變數 (prop)。若要這麼做

1. 請實作「cm.ssf」變數 (如上所示)。
1. [啟用 prop。](/help/admin/tools/manage-rs/edit-settings/c-traffic-variables/traffic-var.md)
1. 使用處理規則將內容變數對應至 prop。

   1. 前往&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝」]**，然後選取報表套裝。
   1. 依序按下&#x200B;**[!UICONTROL 「編輯報表套裝]** > **[!UICONTROL 一般]** > **[!UICONTROL 處理規則」]**。
   1. 按一下&#x200B;**[!UICONTROL 「新增規則」]**。
   1. 在&#x200B;**[!UICONTROL 「一律執行」]**&#x200B;下，以上下文變數「cm.ssf(Context Data)」覆寫已啟用的 prop 值。
   1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。
