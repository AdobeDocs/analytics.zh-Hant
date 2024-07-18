---
title: 分類集概觀
description: 使用分類集管理分類資料。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 66be48d0f41061d259cc53fb835ebd155294a710
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 84%

---

# 分類集概觀

分類集會提供管理分類和規則的單一介面。此工作流程會將在報告套裝設定中建立分類的概念和分類匯入工具的概念相結合，以提供更直覺式的介面來建立和管理分類資料。

**[!UICONTROL 元件]** > **[!UICONTROL 分類集]**

您必須是產品管理員或屬於包含許可權專案[!UICONTROL 報表套裝工具] > [!UICONTROL 分類]的產品設定檔，才能檢視此功能表專案。 請注意，雖然先前的分類管理介面位於[!UICONTROL 管理員]功能表下，但分類設定位於[!UICONTROL 元件]功能表下。

## 改進項目

與分類集一起發布的後端架構包含幾個顯著的改善：

* 縮短處理時間 (72 小時 → 24 小時)
* 重新設計的UI以管理分類
* 未來透過[用於分類資料的 Adobe Analytics 來源連接器](https://experienceleague.adobe.com/en/docs/experience-platform/sources/connectors/adobe-applications/classifications)在 Adobe Experience Platform 中使用分類資料的選項

與分類集一起發布的後端架構也包含幾個顯著的變更：

* 使用瀏覽器或自動匯入時，一定要啟用「[!UICONTROL 衝突時覆寫]」。
* 使用瀏覽器或自動匯入時，不再支援匯入後立即匯出的選項。匯出必須單獨啟動。
* Analytics 2.0 API `GetDimensions`端點現在回傳用於分類的字串識別碼，而不是數值識別碼。還是可以使用數值識別碼，但 Adobe 建議盡可能使用新的字串識別碼。可以使用 `?expansion=hidden` 查詢字串參數擷取數值識別碼。

>[!IMPORTANT]
>
>分類集的效能主要取決於包含資料的唯一關鍵值數量。Adobe 建議在處理包含大量唯一值的變數時務必小心。將多個報告套裝和維度中的變數整合至單一分類集時，尤其需要注意這一點。

分類集包含三個主要區域：

* [**[!UICONTROL 分類集管理員]**](manage/set-manager.md)：建立、編輯和刪除「分類集」。
* [**[!UICONTROL 分類集作業管理員]**](job-manager.md)：檢視分類集作業的狀態並下載匯出檔案。
* [**[!UICONTROL 分類集合併]**](consolidations/manage.md)：將多項分類集合併為單一的分類集。
