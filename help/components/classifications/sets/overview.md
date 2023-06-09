---
title: 分類設定概觀
description: 使用分類設定來管理分類資料。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: 05243d37d252274d88650566de049327ff2bd439
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 26%

---

# 分類設定概觀

分類設定提供管理分類和規則的單一介面。 此工作流程結合了在報表套裝設定中建立分類的概念與分類匯入程式的概念，以提供更直覺式的介面來建立和管理分類資料。

**[!UICONTROL 元件]** > **[!UICONTROL 分類設定]**

隨「分類設定」發行的後端架構包含幾項顯著改善：

* 縮短處理時間(72小時→24小時)
* 能夠使用「分類設定」UI
* 未來透過[用於分類資料的 Adobe Analytics 來源連接器](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html?lang=zh-Hant) 在 Adobe Experience Platform 中使用分類資料的選項

隨「分類設定」發行的後端架構也包含幾項顯著變更：

* 使用瀏覽器或自動匯入時，[!UICONTROL 發生衝突時覆寫]」一律啟用。
* 使用瀏覽器或自動匯入時，不再支援匯入後立即匯出的選項。 匯出必須單獨啟動。
* Analytics 2.0 API `GetDimensions`端點現在回傳用於分類的字串識別碼，而不是數值識別碼。還是可以使用數值識別碼，但 Adobe 建議盡可能使用新的字串識別碼。可以使用 `?expansion=hidden` 查詢字串參數擷取數值識別碼。

>[!IMPORTANT]
>
>分類設定的效能主要取決於包含資料的不重複索引鍵值數目。 Adobe建議在處理包含大量不重複值的變數時務必謹慎。 將多個報告套裝和維度的變數合併為單一分類集時，應特別注意。

「分類設定」包含三個主要區域：

* [**[!UICONTROL 分類設定管理員]**](manage/set-manager.md)：建立、編輯和刪除分類設定。
* [**[!UICONTROL 分類設定作業管理員]**](job-manager.md)：檢視分類設定作業的狀態並下載匯出檔案。
* [**[!UICONTROL 分類設定合併]**](consolidations/manage.md)：將多個分類集合併為單一分類集。
