---
description: 套用特定維度字詞的篩選。
title: 特定篩選
uuid: b3a8187a-3d59-4da0-abca-e933664332e3
feature: Report Builder
role: User, Admin
exl-id: e5f2d67c-3add-4d51-8a76-ee3b2a6eef94
TQID: https://experienceleague.adobe.com/yNIeTJwwWtjXkbi47lX1Ve-Rbz6lF1PazD4YxxXa0Ac
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 336
ht-degree: 64%

---

# 特定篩選

{{legacy-arb}}

套用特定維度字詞的篩選。

您可以建立符合確切條件的篩選器，以搜尋特定維度專案。 例如，您可以建立以下類型的篩選器：[!DNL homepage.htm]、[!DNL contact_us.html]、[!DNL corporate_info.html] 中的頁面。

**建立特定的篩選**

1. 建立或編輯請求，然後前往[!UICONTROL 「請求精靈: 步驟 2」]。

   ![熒幕擷圖顯示篩選依據選項：應用程式、使用者和專案。](/help/admin/tools/assets/filter.png)

1. 在[!UICONTROL 「請求精靈: 步驟 2」]中，於格線內按一下維度旁的連結，然後選擇&#x200B;**[!UICONTROL 「篩選」]**。

1. 啟用&#x200B;**[!UICONTROL 特定]**。

   ![選取特定選項的[選擇頁面]對話方塊熒幕擷圖。](assets/choose_page_specific01.png)

1. 啟用下列其中一個特定選項：

   * **從儲存格範圍：**&#x200B;可讓您選擇儲存格中的資料。 您可以選取：
      * **範圍內的所有儲存格：**&#x200B;可讓您映射範圍內的每一個儲存格。 說明文字說明必須選取多少儲存格群組。 若要對應多個儲存格群組，請在連續選取時按下Ctrl鍵。 如果必須對應的範圍只包含一個儲存格，則此選項是唯一可用的選項
      * **範圍的第一個儲存格：**&#x200B;您只需要選擇範圍左上角的儲存格，然後再選擇資料的方向。 此外，如果請求有多個期間，您可以選擇期間的方向，並選擇是否要在期間之間跳過一組儲存格數目。
   * **從清單：**&#x200B;可讓您從可新增資料的清單選擇資料。
1. 如果您啟用&#x200B;**[!UICONTROL 「從清單」]**，請選擇任何可用的清單項目或按一下&#x200B;**[!UICONTROL 「新增」]**。

   在按一下「**[!UICONTROL 新增]**」時，「[!UICONTROL 從清單選擇]」表單會針對目前的請求日期範圍顯示可用的維度項目清單 (僅限前 10,000 個項目)。 您可以搜尋這些項目或按一下&#x200B;**[!UICONTROL 更多...]**，此選項會顯示「[!UICONTROL 搜尋表單]」以供您建立更詳細的維度搜尋。
1. 在[!UICONTROL 「從清單選擇」]中按一下&#x200B;**[!UICONTROL 「確定」]**。
1. 如果您需要的話，可以在[!UICONTROL 「選擇頁面」]表單中儲存「特定」篩選，然後按一下&#x200B;**[!UICONTROL 「確定」]**。
