---
description: 協助尋找您的Google Ads帳戶ID與Microsoft Advertising帳戶識別碼的指示。
title: 找出您的帳戶 ID
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
TQID: 'https://experienceleague.adobe.com/5Z2hL08Ynl9M6abCm2bchArEOIYDz0cPTRIxQeqLbZ8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
subfeature_v2:
  - id: fe0a7292-80bc-407a-b456-64170267d1cc
  - id: a9364d69-0c51-44bf-8b5f-6d99c04493b8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 344
ht-degree: 22%

---

# 找出您的帳戶 ID {#locate-your-account-ids}

瞭解如何找出您的Google Ads和Microsoft Advertising帳戶ID。

## Google Ads (AdWords) {#google}

>[!IMPORTANT]
>
>Google Ads使用兩種型別的帳戶：
>
>- MCC （我的使用者端中心）帳戶，以及
>- 標準帳戶。
>
>為了與Adobe Analytics整合，**您必須使用標準帳戶登入**，而不是MCC帳戶登入。 原因在於MCC帳戶就像是「傘狀」帳戶，使用者只要憑藉同一組登入資訊，就能存取多個Google Ads帳戶，但標準帳戶登入資訊的每組登入資訊只能存取一個帳戶。 雖然Google支援連結一個電子郵件來管理5個帳戶，但Advertising Analytics尚未支援此功能。 一個電子郵件只能與一個Google Ads帳戶連結。

按一下右上角的「帳戶」圖示，檢視Google Ads帳戶號碼（客戶ID）。

![Google廣告管理員帳戶](assets/google-account.png)

## Microsoft Advertising (Bing) {#microsoft}

>[!NOTE]
>
>如果您的Microsoft Advertising （先前稱為Bing）帳戶使用Google匯入功能，請務必更新正確的追蹤字串。 追蹤字串不會自動從Google版本更新為正確的Microsoft Advertising追蹤字串，而且可能會產生未指定的資料。 如需詳細資訊，請參閱Microsoft Advertising說明中的[從Google Ads匯入的專案](https://help.ads.microsoft.com/apex/index/3/en/50851/)。

**[!UICONTROL 帳戶ID]**&#x200B;和&#x200B;**[!UICONTROL 管理員帳戶ID]**&#x200B;都是必要的。

- **[!UICONTROL 帳戶ID]**&#x200B;位於&#x200B;**[!UICONTROL 設定]** > **[!UICONTROL 帳戶設定]** > **[!UICONTROL 帳戶ID]**&#x200B;之下。 確定您使用[!UICONTROL 帳號ID]，而非[!UICONTROL 帳號]。
- **[!UICONTROL 管理員帳戶ID]**&#x200B;位於&#x200B;**[!UICONTROL 設定]** > **[!UICONTROL 管理員帳戶設定]** > **[!UICONTROL 管理員帳戶ID]**&#x200B;之下。 請確定您使用[!UICONTROL 管理員帳號ID]，而非[!UICONTROL 管理員帳號]。

![Microsoft Advertising導覽](assets/bing-id.png)

>[!CONTEXTUALHELP]
>id="adanalytics_ma_account_id"
>title="帳戶 ID"
>abstract="「帳戶 ID」是位於 Microsoft Advertising 介面中的數值。 導覽至「設定 > 帳戶設定 > 帳戶 ID」即可找到。"

>[!CONTEXTUALHELP]
>id="adanalytics_ma_manager_account_id"
>title="管理員帳戶 ID"
>abstract="「管理員帳戶 ID」是位於 Microsoft Advertising 介面中的數值。 導覽至「設定 > 管理員帳戶設定 > 管理員帳戶 ID」即可找到。"
