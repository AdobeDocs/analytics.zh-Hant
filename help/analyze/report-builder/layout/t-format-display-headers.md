---
description: 您可以為報表命名，以及設定列和欄標題的顯示方式。「樞紐配置」和「自訂配置」等類型備有「格式選項」連結供您使用。
seo-description: 您可以為報表命名，以及設定列和欄標題的顯示方式。「樞紐配置」和「自訂配置」等類型備有「格式選項」連結供您使用。
seo-title: 格式顯示標題
solution: Analytics
title: 格式顯示標題
topic: Report Builder
uuid: cd0e167b-9463-43fd-87b2-724d1c79de68
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 格式顯示標題

您可以為報表命名，以及設定列和欄標題的顯示方式。「樞紐配置」和「自訂配置」等類型備有「格式選項」連結供您使用。

1. 在[!UICONTROL 「請求精靈: 步驟 1」]中建立請求。
1. Click **[!UICONTROL Next]**.
1. 在[!UICONTROL 「請求精靈: 步驟 2」]表單中，根據需求將維度和度量資料新增至請求。
1. Click **[!UICONTROL Format Options]**.
1. 設定「[!UICONTROL 顯示]」選項:  

   | 元素 | 說明 |
   |--- |--- |
   | 報表名稱 | Displays either the name of the report type you selected from the tree in the  Request Wizard: Step 1 (for example, [!DNL Traffic Report]), or the name you type in the [!DNL Name this Request] field. |
   | 篩選參數 | 顯示維度篩選，例如搜尋篩選。 |
   | 區段 | 顯示區段參數。 |
   | 資料時近 | 顯示資料時近參數。例如:    Data Recency: Page Views (1.5 hr ago), Exits (30 mins ago)  See [Options](../../../analyze/report-builder/options.md) for information about current data processing. |

   至於顯示順序，如果「[!UICONTROL 列標籤]」格線 (於步驟 2) 含有項目，則會最先顯示在請求中。如果不含項目，系統會使用「[!UICONTROL 欄標籤]」格線中的第一個項目。如果沒有任何列項目或欄項目，系統會顯示「[!UICONTROL 度量]」格線中的第一個項目。

   **顯示列與欄的標題:**&#x200B;新增列和欄以顯示這些項目。

   在 3.11 版中，您可以顯示每個項目的標題。第 4 版會顯示所有項目或不顯示任何項目。如果您在 3.11 版中建立請求並在 4.x 版中開啟，Report Builder 會在步驟 2 提示您針對遺失標題的項目更新一個儲存格的範圍。

   **將標題變更為 Excel 自動篩選:** 僅適用於已顯示列和欄標題時。此設定會建立 Excel 自動篩選，並將篩選套用至 Report Builder 針對此請求傳回的資料。

   >[!NOTE]
   >
   >Excel僅支援一個工作表的自動篩選。如果在已有自動篩選的工作表中建立新的自動篩選，Excel 不會警告您即將取代現有的自動篩選。

   **執行自動外框:** 將 Report Builder 傳回的日期從清單檢視轉換為樹狀檢視。

   **為此請求命名:**&#x200B;讓您為請求輸入使用者定義的名稱，或使用在步驟 1 選擇的預設名稱。這個名稱會成為「[!UICONTROL 請求管理員]」中的「[!UICONTROL 報表]」名稱。請參閱[為請求命名](../../../analyze/report-builder/layout/name-a-request.md#concept_37277AFB63EA4541B6FD93A5B713D82D)。

1. Click **[!UICONTROL OK]**.
