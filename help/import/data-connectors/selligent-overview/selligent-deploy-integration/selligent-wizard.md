---
description: 若要啟動整合，您必須在「資料連接器」介面中完成「選擇性整合」精靈。
seo-description: 若要啟動整合，您必須在「資料連接器」介面中完成「選擇性整合」精靈。
seo-title: 完成整合精靈
solution: Analytics
title: 完成整合精靈
uuid: cb588162-18c6-4259-b802-50bc3816cc95
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 完成整合精靈{#completing-the-integration-wizard}

若要啟動整合，您必須在「資料連接器」介面中完成「選擇性整合」精靈。

1. 導覽至Adobe Experience cloud中的「資料連接器」區域。

   ![](assets/selligent-data_connectors.png)

1. 在「 **[!UICONTROL 新增整合]**」下方，將Selligent外掛程式拖放至Adobe Experience Cloud。

   ![](assets/selligent-add_integration.png)

   這將開啟Selligent Data Connector整合。

1. **整合設定**:選擇所要的報表套裝，並在「整合設定」下提供整合 **[!UICONTROL 的名稱]**。

1. 在「 **[!UICONTROL 自訂值]**」下方，填寫您所 [有與Selligent帳戶相關的資訊](../../selligent-overview/selligent-activation/selligent-prereqs-seligent.md#concept-071c594b1bcc465cbce7a6fda3f1d829)。

   ![](assets/selligent-general_settings.png)

1. **變數對應**:從下拉式選 [單中選擇適當的保留eVar](../../selligent-overview/selligent-activation/selligent-configure-variables.md#concept-907c2bdbed274c11a46d4cc323ef0238) 和事件：

   ![](assets/selligent-variables.png)

1. **資料設定**:除了3個自動化合作夥伴區 **[!UICONTROL 段外]** ，您可在「您的區段」下選擇 **[!UICONTROL 您自己的區段]** 。

1. 此整合可能需要將數個資料點下載至您的Selligent帳戶。 您可以選擇在「存取請求」下授予相 **[!UICONTROL 同的存取權]**。
1. 在「 **[!UICONTROL 資料收集]**」下方，選擇自動或手動解決方案（JavaScript外掛程式），從著陸頁面URL收集查詢字串參數。 如果您選擇自動化解決方案，請為「訊息ID」和「收件者ID」輸入查詢字串參數，其分別為MID和RID。 如需JavaScript外掛程式，請連絡您的Adobe顧問。
1. **報表設定**:在「控 **[!UICONTROL 制面板產生]**」(Dashboard Generation)下，選中該框以自動為您生成「選擇」控制面板。

   ![](assets/selligent-report_settings.png)

1. 檢閱整合摘要，然後按一 **[!UICONTROL 下啟動]**。

