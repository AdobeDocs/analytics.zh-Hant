---
description: 您可以為報表命名，以及設定列和欄標題的顯示方式。「樞紐配置」和「自訂配置」等類型備有「格式選項」連結供您使用。
title: 顯示標題格式
topic: Report builder
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 顯示標題格式

您可以為報表命名，以及設定列和欄標題的顯示方式。「樞紐配置」和「自訂配置」等類型備有「格式選項」連結供您使用。

1. 在上建立請求 [!UICONTROL Request Wizard: Step 1]。
1. 按一下 **[!UICONTROL Next]**.
1. On the [!UICONTROL Request Wizard: Step 2] form, add dimensions and metrics data to the request, as desired.
1. 按一下 **[!UICONTROL Format Options]**.
1. Configure the [!UICONTROL Display] options:

   | 元素 | 說明 |
   |--- |--- |
   | 報告名稱 | 顯示您在「請求精靈: 步驟 1」的樹狀檢視中選擇的報表類型名稱 (如「[!DNL Traffic Report]」)，或您在「[!DNL Name this Request]」欄位中輸入的名稱。 |
   | 篩選參數 | 顯示維度篩選，例如搜尋篩選。 |
   | 區段 | 顯示區段參數。 |
   | 資料時近 | 顯示資料時近參數。例如:資料時近：頁面檢視 (1.5 小時前)、退出點 (30分鐘前)  如需目前資料處理的資訊，請參閱[選項](/help/analyze/report-builder/options.md)。 |

   Regarding display order, if the [!UICONTROL Row Label] grid (on Step 2) contains an item, it is displayed first in the request. If not, the system uses the first item present in the [!UICONTROL Column Label] grid. If no row or column items exist, the first item in the [!UICONTROL Metrics] grid is displayed.

   **顯示列與欄的標題：**&#x200B;新增列和欄以顯示這些項目。

   在 3.11 版中，您可以顯示每個項目的標題。第 4 版會顯示所有項目或不顯示任何項目。如果您在 3.11 版中建立請求並在 4.x 版中開啟，Report Builder 會在步驟 2 提示您針對遺失標題的項目更新一個儲存格的範圍。

   **將標題變更為 Excel 自動篩選：**&#x200B;僅適用於已顯示列和欄標題時。此設定會建立 Excel 自動篩選，並將篩選套用至 Report Builder 針對此請求傳回的資料。

   >[!NOTE]
   >
   >Excel 僅支援在每個工作表中使用一個自動篩選。如果在已有自動篩選的工作表中建立新的自動篩選，Excel 不會警告您即將取代現有的自動篩選。

   **執行自動外框：**&#x200B;將 Report Builder 傳回的日期從清單檢視轉換為樹狀檢視。

   **為此請求命名：**&#x200B;讓您為請求輸入使用者定義的名稱，或使用在步驟 1 選擇的預設名稱。此名稱將作為 [!UICONTROL Report] 名稱顯示在 [!UICONTROL Request Manager]中。 See [Name a Request](/help/analyze/report-builder/layout/name-a-request.md).

1. 按一下 **[!UICONTROL OK]**.
