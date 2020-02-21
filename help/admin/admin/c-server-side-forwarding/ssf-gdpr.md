---
description: 'null'
title: GDPR/ePrivacy 法規遵循與伺服器端轉送
uuid: 1b90c567-3321-4dbd-a699-38c04e809fa4
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# GDPR/ePrivacy 法規遵循與伺服器端轉送

本節內容說明，根據[歐盟 Cookie 法規規範](https://ec.europa.eu/ipg/basics/legal/cookies/index_en.htm) (已於 2017 年 9 月 30 日生效) 近期內推動之伺服器端轉送的增強功能。

伺服器端轉送可用於即時將資料從 Adobe Analytics 分享至其他 [!DNL Experience Cloud Solutions] (例如 Audience Manager)。啟用伺服器端轉送功能後，可在資料收集程序期間期間，讓 Analytics 推送資料到其他 Experience Cloud 解決方案，以及讓這些解決方案推送資料到 Analytics。

直到最近，伺服器端轉送仍無法在同意與預先同意的事件/點擊間描述。自 2018 年 11 月 1 日起，您做為資料控管單位 (Adobe Analytics 客戶)，可選擇將預先同意的資料限制在 Adobe Analytics，並防止其轉送至 AAM。如此一來，實作環境變數有別於以往，可讓您標記未獲許可的點擊。設定變數時，可防止這些點擊在收到許可前傳送至 AAM。

這個新的上下文變數「`cm.ssf=1`」存在於點擊時，系統會標記該點擊，且不會將其從伺服器端轉送至 AAM。反之，若此字串並未出現在點擊，系統會將該點擊轉送至 AAM。

伺服器端轉送是雙向的，這代表當其適用於點擊，而系統將該點擊轉送至 AAM 時，Audience Analytics 會從 AAM 接收到該點擊的區段資訊，並將該資訊傳送回 Analytics。如此一來，任何非從 Analytics 伺服器端轉送至 AAM 的點擊，將不會加入 AAM 的 ID 區段清單。因此，將會存在不會從 AAM 取得區段 ID 資訊的流量/點擊子集。

## 實作詳細資料 {#section_FFA8B66085BF469FAB5365C944FE38F7}

請根據您的實作方法，遵循下列步驟。

| 實作方法 | 步驟 |
|--- |--- |
| Adobe Experience Platform Launch | 假設您已安裝 Adobe Analytics 擴充功能，請在「規則」的「動作」設定中，將下方的上下文資料變數定義加到自訂程式碼編輯器： <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/> 注意： 若客戶不同意目標式行銷，請定義 contextdata 變數，並將其設為「1」。如果客戶同意目標式行銷，請將 `contextdata` 變數設為&#x200B;*「0」*。 |
| DTM | 將內容變數定義新增至自訂頁面程式碼編輯器：<br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注意：若客戶不同意目標式行銷，請定義 contextData 變數，並將其設為「1」。對於同意目標式行銷的客戶，請將 contextData 變數設為「0」。 |
| AppMeasurement | 將內容資料變數定義新增至 AppMeasurement.js 檔案：  <br/>`s.contextData['cm.ssf']&nbsp;=&nbsp;'1' `<br/>注意：若客戶不同意目標式行銷，請定義 contextData 變數，並將其設為「1」。對於同意目標式行銷的客戶，請將 contextData 變數設為「0」。 |

## 報表 (選用) {#section_6AD4028EC11C4DABA2A34469DDC99E89}

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

