---
title: 「分類設定」概觀
description: 使用「分類設定」管理分類資料。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
source-git-commit: 2ba6ffc7f632975ca16fa02ee79d467d4d53f076
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 45%

---

# 「分類設定」概觀

「分類設定」會提供管理分類和規則的單一介面。此工作流程會將在報告套裝設定中建立分類的概念和分類匯入工具的概念相結合，以提供更直覺式的介面來建立和管理分類資料。

**[!UICONTROL 元件]** > **[!UICONTROL 分類設定]**

>[!NOTE]
>
>分類集將可供所有將報告套裝移轉到新分類架構的客戶使用。如需詳細資訊，請聯絡 Adobe 客戶服務或您的客戶經理。

隨分類集發行的後端架構包含幾項顯著改善：

* 大幅縮短處理時間(72小時→ 24小時)
* 使用分類集UI的功能
* 未來在Adobe Experience Platform中使用分類資料的選項，透過 [Adobe Analytics來源連接器（分類資料）](https://experienceleague.adobe.com/docs/experience-platform/sources/connectors/adobe-applications/classifications.html)

隨分類集發佈的後端架構也包含數項重大變更：

* 使用瀏覽器或FTP匯入時，「[!UICONTROL 衝突時覆蓋]「一律啟用。
* 使用瀏覽器或FTP匯入時，不再支援在匯入後立即匯出的選項。 導出必須單獨啟動。
* Analytics 2.0 API `GetDimensions` 端點現在會為分類傳回字串識別碼，而非數值識別碼。 數值識別碼仍可使用，但Adobe建議盡可能使用新的字串識別碼。 數值識別碼可透過 `?expansion=hidden` 查詢字串參數。


「分類設定」包含兩個主要區域：

* [**[!UICONTROL 分類設定管理員]**](set-manager.md)：建立、編輯和刪除「分類設定」。
* [**[!UICONTROL 分類設定作業管理員]**](job-manager.md)：檢視分類設定作業的狀態並下載匯出檔案。
