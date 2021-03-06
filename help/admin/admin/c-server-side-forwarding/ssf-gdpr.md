---
description: 解釋由歐盟 Cookie 合規性法規推動的伺服器端轉送的增強功能。
title: GDPR/ePrivacy 法規遵循與伺服器端轉送
feature: Server-Side Forwarding
exl-id: 54e43a16-8f15-4ee8-9aa2-579af30be2c9
source-git-commit: ee56267979979f8e03b1c6a0d849ccf994599024
workflow-type: ht
source-wordcount: '541'
ht-degree: 100%

---

# GDPR/ePrivacy 法規遵循與伺服器端轉送

本節內容將解釋[歐盟 Cookie 合規性法規](https://wikis.ec.europa.eu/display/WEBGUIDE/04.+Cookies+and+similar+technologies) (已於 2017 年 9 月 30 日生效) 推動之伺服器端轉送的增強功能。

伺服器端轉送可用於即時將資料從 Adobe Analytics 分享至其他 [!DNL Experience Cloud Solutions] (例如 Audience Manager)。啟用伺服器端轉送功能後，也可在資料收集過程中讓 Analytics 推送資料到其他 Experience Cloud 解決方案，並讓這些解決方案推送資料到 Analytics。

在過去，伺服器端轉送無法區分同意與預先同意的事件/點擊。 自 2018 年 11 月 1 日起，您做為資料控管單位 (Adobe Analytics 客戶)，可選擇將預先同意的資料限制在 Adobe Analytics，並防止其轉送至 AAM。新的實作內容變數可讓您在未收到同意的地方標記點擊。 設定變數時，可防止這些點擊在收到許可前傳送至 AAM。

這個新的上下文變數「`cm.ssf=1`」存在於點擊時，系統會標記該點擊，且不會將其從伺服器端轉送至 AAM。反之，若此字串並未出現在點擊，系統會將該點擊轉送至 AAM。

伺服器端轉送是雙向的，這代表當其適用於點擊，而系統將該點擊轉送至 AAM 時，Audience Analytics 會從 AAM 接收到該點擊的區段資訊，並將該資訊傳送回 Analytics。如此一來，任何非從 Analytics 伺服器端轉送至 AAM 的點擊，將不會加入 AAM 的 ID 區段清單。因此，將會存在不會從 AAM 取得區段 ID 資訊的流量/點擊子集。

## 實作詳細資料 {#section_FFA8B66085BF469FAB5365C944FE38F7}

請根據您的實作方法，遵循下列步驟。

| 實作方法 | 步驟 |
|--- |--- |
| Adobe Experience Platform 中的標籤 | 假設您已安裝 Adobe Analytics 擴充功能，請在「規則」的「動作」設定中，將下方的內容資料變數定義加到自訂程式碼編輯器：<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' ` <br/>注意：若客戶不同意目標式行銷，請定義 contextdata 變數，並將其設為「1」。 如果客戶同意目標式行銷，請將 `contextdata` 變數設為 *0*。 |
| AppMeasurement | 將內容資料變數定義新增至 AppMeasurement.js 檔案：    <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注意：若客戶不同意目標式行銷，請定義 contextData 變數，並將其設為「1」。對於同意目標式行銷的客戶，請將 contextData 變數設為「0」。 |

## 報告 (選用) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

透過 Adobe Analytics 報表，您可以瞭解經過同意而從伺服器端轉送的流量大小，以及未經過同意且未轉送至 AAM 的流量大小。

若要設定此類型報表，請將新的內容變數，透過處理規則對應至自訂流量變數 (prop)。若要這麼做

1. 請實作「cm.ssf」變數 (如上所示)。
1. [啟用 prop。](/help/admin/admin/c-traffic-variables/traffic-var.md)
1. 使用處理規則將內容變數對應至 prop。

   1. 前往&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理員]** > **[!UICONTROL 報表套裝」]**，然後選取報表套裝。
   1. 依序按下&#x200B;**[!UICONTROL 「編輯報表套裝]** > **[!UICONTROL 一般]** > **[!UICONTROL 處理規則」]**。
   1. 按一下&#x200B;**[!UICONTROL 「新增規則」]**。
   1. 在&#x200B;**[!UICONTROL 「一律執行」]**&#x200B;下，以上下文變數「cm.ssf(Context Data)」覆寫已啟用的 prop 值。
   1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。
