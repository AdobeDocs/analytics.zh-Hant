---
description: 說明如何將 Report Builder 發佈的資產帶入 Power BI Desktop
title: 將已發佈的資產帶入 Power BI Desktop
feature: Report Builder
role: User, Admin
exl-id: ce6020df-caf4-4cd2-8086-4357309e5bbb
TQID: https://experienceleague.adobe.com/fS1xnUciNh8LdPw2ENYMJTDGLqo3C8u4lu39X-GYuZE
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 222
ht-degree: 68%

---

# 將已發佈的資產帶入 Power BI Desktop

{{legacy-arb}}

說明如何將 Report Builder 發佈的資產帶入 Power BI Desktop

## 先決條件 {#section_BDFDAE1E300B429FB6EBCB21AD1383A0}

* 您必須安裝最新的Power BI Desktop版本（2017年4月發行）
* 此程式假設您已將Report Builder格式的表格或請求發佈至Power BI服務。

## 程序 {#section_CB03E6E1B066457EA0F6FC08FFF5EFDD}

在2017年4月的Power BI Desktop更新中，Microsoft發行了連線至Power BI服務中資料集的功能。 這項功能可讓您從已發佈至雲端的現有資料集建立新報告。 您可以善用此功能來加強共同作業，並減少整個團隊的重複工作。

1. 在 Power BI Desktop 中，前往&#x200B;**[!UICONTROL 「檔案]** > **[!UICONTROL 選項與設定]** > **[!UICONTROL 選項]** > **[!UICONTROL 預覽功能」]**。
1. 啟用「**[!UICONTROL Power BI 服務即時連線]**」，然後按一下「**[!UICONTROL 確定]**」。 ![按一下「Power BI 服務即時連線」，然後按一下「確定」。](assets/bi-preview-features.png)

1. 重新啟動 Power BI Desktop。
1. 重新啟動後，前往&#x200B;**[!UICONTROL 「首頁]** > **[!UICONTROL 取得資料]** > **[!UICONTROL 更多...」]**。
1. 搜尋 **[!UICONTROL Power BI 服務]**&#x200B;並加以選取。
1. 在&#x200B;**[!UICONTROL 「Microsoft Power BI 服務]** > **[!UICONTROL 工作區」]**&#x200B;下，選取您先前從 Report Builder 發佈的資料集。

如需詳細資訊，請參閱「[Microsoft 部落格文章](https://powerbi.microsoft.com/en-us/blog/connecting-to-datasets-in-the-power-bi-service-from-desktop/)」。
