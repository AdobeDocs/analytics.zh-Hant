---
description: 您可以實施自訂方法，設定 s.visitorID 變數以識別訪客。
keywords: Analytics 實施
seo-description: 您可以實施自訂方法，設定 s.visitorID 變數以識別訪客。
seo-title: 自訂訪客 ID
solution: Analytics
title: 自訂訪客 ID
topic: 開發人員和實施
uuid: 49881e27-0418-4ef-a092-dcc3 db923 f40
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 自訂訪客 ID

您可以實施自訂方法，設定 s.visitorID 變數以識別訪客。

在您有獨特方式來識別訪客的網站上，可以使用自訂訪客 ID。範例是當使用者以使用者名稱和密碼登入網站時產生的 ID。

如果能夠遞送及管理使用者的 [!UICONTROL visitor IDs]，則可以使用下列方法來設定 ID:

| 方法 | 說明 |
|---|---|
| [s.visitorID](/help/implement/js-implementation/c-variables/page-variables.md) 變數 | 如果在瀏覽器上使用 JavaScript，或如果您是使用任何其他 AppMeasurement 程式庫，則可在資料收集變數中設定訪客 ID。 |
| 影像要求上的查詢字串參數 | 這可讓您透過硬式編碼影像請求的 [!UICONTROL vid 查詢字串]參數，將[!UICONTROL 訪客 ID] 傳送至 Adobe。 |
| 資料插入 API | On devices using wireless protocols that don't accept JavaScript, you can send an XML post containing the `<visitorid/>` XML element to Adobe collection servers from your servers. |
| URL 重寫和 VISTA | 有些部署架構可在您無法設定 Cookie 時，提供使用 URL 重寫以維護工作階段狀態的支援。在這種情況下，Adobe 工程服務可實施 [!DNL VISTA] 規則以在頁面的 URL 中尋找工作階段值，並在格式化後將其放入 [!UICONTROL visid] 值中。 |
>[!CAUTION]
>**自訂訪客ID必須具備足夠精細/獨特**&#x200B;的特性：無效的自訂訪客ID實作可能導致資料錯誤和報告效能不佳。如果自訂訪客ID不是唯一或精細的，或者不正確地設為常見預設值，例如字串「NULL」或「0」，則Adobe Analytics將會將許多不同訪客的點擊視為單一訪客。此情況造成資料不正確，訪客計數過低，且訪客區段無法正確運作。不充足的粒度自訂訪客ID也可防止資料在Analytics報告叢集中的節點間正確擴散。在此情況下，一個節點會超載，並無法及時處理報告請求。報表套裝的所有報表最終都會失敗。<br>建置自訂訪客ID不會立即影響報告效能，因為Analytics通常可處理數個月的不平衡資料；但是，在建置不當的自訂訪客ID值時，可能會因為Analytics停用受影響報告套裝的處理而造成問題。</br><br>實施者應遵循單一自訂訪客ID值不應計入超過1%報表套裝流量的准則。Although the 1% guideline is sufficient for most report suites, the actual limit that might cause reporting performance to be impacted may be lower than 1% for very large report suites.</br>
