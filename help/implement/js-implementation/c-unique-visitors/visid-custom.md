---
description: 您可以實施自訂方法，設定 s.visitorID 變數以識別訪客。
keywords: Analytics Implementation
title: 自訂訪客 ID
topic: Developer and implementation
uuid: 49881e27-0418-4ecf-a092-dcc3db923f40
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 自訂訪客 ID

您可以實施自訂方法，設定 s.visitorID 變數以識別訪客。

在您有獨特方式來識別訪客的網站上，可以使用自訂訪客 ID。範例是當使用者以使用者名稱和密碼登入網站時產生的 ID。

如果能夠遞送及管理使用者的 [!UICONTROL visitor IDs]，則可以使用下列方法來設定 ID:

| 方法 | 說明 |
|---|---|
| [s.visitorID](/help/implement/js-implementation/page-variables/page-variables.md) 變數 | 如果在瀏覽器上使用 JavaScript，或如果您是使用任何其他 AppMeasurement 程式庫，則可在資料收集變數中設定訪客 ID。 |
| 影像要求上的查詢字串參數 | 這可讓您透過硬式編碼影像請求的 [!UICONTROL vid 查詢字串]參數，將[!UICONTROL 訪客 ID] 傳送至 Adobe。 |
| 資料插入 API | 在使用無線通訊協定，沒有接受 JavaScript 的裝置上，您可以從您的伺器將包含 `<visitorid/>` XML 元素的 XML 貼文傳送至 Adobe 收集伺服器。 |
| URL 重寫和 VISTA | 有些部署架構可在您無法設定 Cookie 時，提供使用 URL 重寫以維護工作階段狀態的支援。在這種情況下，Adobe 工程服務可實施 [!DNL VISTA] 規則以在頁面的 URL 中尋找工作階段值，並在格式化後將其放入 [!UICONTROL visid] 值中。 |
>[!CAUTION]
>**自訂訪客 ID 的精細/獨特程度必須足夠**: 無效的自訂訪客 ID 實施會導致不正確的資料和不良的報表效能。如果自訂訪客ID不夠獨特或精細，或未正確設定為常見預設值，例如字串「NULL」或「0」,Adobe Analytics會將來自許多不同訪客的點擊視為單一訪客。 此情況會導致不正確的資料，訪客計數會太低，且該訪客的區段無法正常運作。精細程度不足的自訂訪客 ID 也會讓資料無法正確分散到 Analytics 報表叢集中的各個節點。在此情況下，一個節點會變成超載，而無法及時地處理報表要求。最後，該報表套裝的所有報表作業都會失敗。<br>建置不當的自訂訪客ID可能不會立即影響報告效能，因為Analytics通常可處理數個月的不平衡資料；但是，隨著時間推移，實作不佳的自訂訪客ID值可能會成問題，以至於Analytics必須停用受影響報表套裝的處理。</br><br>實施者應遵循以下原則：絕不應將單一自訂訪客ID值計入超過報表套裝流量1%。 雖然此 1% 準則對大多數的報表套裝來說已經足夠，但若為非常大型的報表套裝，可能導致報表效能受到影響的實際上限或許低於 1%。</br>
