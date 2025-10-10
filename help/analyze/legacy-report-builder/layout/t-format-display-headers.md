---
description: 瞭解如何為報表命名並設定如何顯示列和欄標題。
title: 如何格式化顯示標題
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
feature: Report Builder
role: User, Admin
exl-id: 168daa6b-965c-4f8b-97b7-651a7ad55d6c
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '409'
ht-degree: 71%

---

# 顯示標題格式

{{legacy-arb}}

您可以為報表命名，以及設定列和欄標題的顯示方式。「樞紐配置」和「自訂配置」等類型備有「格式選項」連結供您使用。

1. 在[!UICONTROL 「請求精靈: 步驟 1」]中建立請求。
1. 按&#x200B;**[!UICONTROL 「下一步」]**。
1. 在[!UICONTROL 「請求精靈: 步驟 2」]表單中，根據需求將維度和度量資料新增至請求。
1. 按一下&#x200B;**[!UICONTROL 「格式選項」]**。
1. 設定[!UICONTROL 「顯示」]選項：

   | 元素 | 說明 |
   |--- |--- |
   | 報告名稱 | 顯示您在「請求精靈: 步驟 1」的樹狀檢視中選擇的報表類型名稱 (如「[!DNL Traffic Report]」)，或您在「[!DNL Name this Request]」欄位中輸入的名稱。 |
   | 篩選參數 | 顯示維度篩選，例如搜尋篩選。 |
   | 區段 | 顯示區段參數。 |
   | 資料時近 | 顯示資料時近參數。例如：    資料時近：頁面檢視（1.5小時前）、退出點（30分鐘前）如需目前資料處理的資訊，請參閱[選項](/help/analyze/legacy-report-builder/options.md)。 |

   至於顯示順序，如果「[!UICONTROL 列標籤]」格線 (於步驟 2) 含有項目，則會最先顯示在請求中。如果不含項目，系統會使用「[!UICONTROL 欄標籤]」格線中的第一個項目。如果沒有任何列項目或欄項目，系統會顯示「[!UICONTROL 度量]」格線中的第一個項目。

   **顯示列與欄的標題：**&#x200B;新增列和欄以顯示這些項目。

   在 3.11 版中，您可以顯示每個項目的標題。第 4 版會顯示所有項目或不顯示任何項目。如果您在3.11版中建立請求，並在4.x版中將其開啟，Report Builder會在步驟2中提示您為缺少標題的專案更新一個儲存格的範圍。

   **將標題變更為 Excel 自動篩選：**&#x200B;僅適用於已顯示列和欄標題時。此設定會建立Excel自動篩選，並將其附加至Report Builder針對此請求傳回的資料。

   >[!NOTE]
   >
   >Excel 僅支援在每個工作表中使用一個自動篩選。如果在已有自動篩選的工作表中建立新的自動篩選，Excel 不會警告您即將取代現有的自動篩選。

   **執行自動外框：**&#x200B;將Report Builder傳回的日期從清單檢視轉換為樹狀檢視。

   **為此請求命名：**&#x200B;讓您為請求輸入使用者定義的名稱，或使用在步驟 1 選擇的預設名稱。這個名稱會成為[!UICONTROL 「請求管理員」]中的[!UICONTROL 「報表」]名稱。請參閱[為請求命名](/help/analyze/legacy-report-builder/layout/name-a-request.md)。

1. 按一下「**[!UICONTROL 確定]**」。
