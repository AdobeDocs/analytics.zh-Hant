---
description: 虛擬報告套裝和多套裝標記各有不同優勢。請多加瞭解哪一種最適合您的組織。
keywords: 虛擬報告套裝,VRS
title: 虛擬報告套裝和多套裝標記考量事項
feature: VRS
exl-id: 7e0a1f5b-26ac-438c-b481-33669039efe5
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '1755'
ht-degree: 98%

---

# 虛擬報表套裝和多套裝標記考量事項

虛擬報告套裝 (VRS) 可讓您從收集您數位財產中的資料的報告套裝檢視資料，但永久套用某個區段。

多數情況下，使用虛擬報告套裝就足以取代多套裝標記了。切換至虛擬報告套裝，能夠有效地移除[次要伺服器呼叫](/help/admin/c-server-call-usage/overage-overview.md)的必要性。舉例來說，您的組織有 6 個不同網站，個別都會傳送資料到自己的報告套裝及合併的全域報告套裝。每個網站都會產生次要伺服器呼叫；一個傳送至個別品牌的報告套裝，第二個則傳送到全域報告套裝。不過，您可以單獨將所有網站的資料僅傳送至全域報告套裝後，使用多個虛擬報告套裝來分隔每個品牌。

使用全域報告套裝和 VRS 取代多套裝標記，這樣就能簡化 Adobe Analytics 實作，並降低伺服器呼叫耗用量，這是我們建議使用的最佳做法。但是，VRS 存在一些重大侷限。若要判斷實作全域報告套裝上所建立的虛擬報告套裝是否為適合您使用的方法，下列準則可協助您做出決定。

## 準則

如果您不確定所述的使用案例是否適用於您及您的組織，請洽詢其他的 Adobe Analytics 管理員或 Adobe 客戶經理。他們可協助您評估業務需求並提供建議。

在決定是否使用多套裝標記或虛擬報告套裝時，請考量下列事項：

### 發佈區段至 Adobe Experience Cloud

虛擬報告套裝不支援共用區段至 Adobe Experience Cloud。想要與 Experience Cloud 共用區段的用戶必須具備來源套裝的存取權。

區段目前無法從虛擬報告套裝發佈至 Adobe Experience Cloud 來進行個人化和鎖定目標。如果您有上述目的，發佈區段時都需要來源報告套裝的存取權。舉例來說，您希望用戶僅能存取其所在地理位置的虛擬報告套裝，但卻想要讓對方可從 Adobe Analytics 建立和共用區段至 Adobe Experience Cloud，以便在 Adobe Target 中設定目標。在此情況下，Adobe 建議使用多套裝標記。如果您不介意讓用戶存取全域報告套裝，或您不需要發佈區段供其他解決方案使用，則可使用虛擬報告套裝。

### 即時報表與目前資料

虛擬報告套裝不支援即時報表，因為資料會進行分段。虛擬報告套裝也無法呈現目前資料，因為它不支援分段功能。上述兩項功能都是 Reports &amp; Analytics 專用。

虛擬報告套裝不提供[即時報表](/help/admin/admin/realtime/t-realtime-admin.md)和[目前的資料](/help/technotes/latency.md)。這項限制對於需要在收集資料後的數秒或數分鐘內對 Reports &amp; Analytics 中的趨勢做出回應的用戶有影響。舉例來說，這類用戶可能包括必須在新聞編輯室中，根據即時內容的消耗而調整標題的編輯。如果您的個別報告套裝具有專門的重大即時資料需求，建議使用多套裝標記。即時報表與目前資料仍可用於全域報告套裝。

### 不重複項目上限

如果您的全域報告套裝一併結合了大量網站，您可能會經常遇到細項[流量過低](/help/technotes/low-traffic.md)的情形。如果使用多套裝標記，上述問題只會在全域報告套裝發生 (個別報告套裝會較少發生低流量情形)。如果使用虛擬報告套裝，這項不重複項目上限會與其他項目共用，導致個別報告套裝也發生低流量情形。如果您希望避免大量資料導致低流量，建議使用多套裝標記。

舉例來說，一家大型媒體組織擁有 100 個網頁屬性。每個屬性每月都要發佈數千篇新聞，此外還要託管前幾個月的所有文章。這家組織使用全域報告套裝，eVar1 設為「文章名稱」。在這份報表中，各個屬性每月總計約有 400 萬個不重複文章名稱。若使用虛擬報告套裝，前 500,000 個具有大量流量的值會納入虛擬報告套裝中；其餘的 350 萬個則會落入低流量資料。如果使用多套裝標記，每個個別報告套裝都可以顯示自己的前 50 萬個值。使用多套裝標記和使用虛擬報告套裝，各自的全域報告套裝不重複項目上限是相同的。

Adobe 客戶服務可針對小量維度提高不重複值的上限，藉此徹底解決此問題。如需詳細資訊，請洽詢客戶團隊和客戶服務。

### 在報告套裝間共用變數

虛擬報告套裝沒有自己的維度和量度組合，只會繼承來源報告套裝的內容。全域報告套裝必須擷取所有網站的所有維度和量度。報告套裝目前最多可採用 250 個 eVar 和 1000 個自訂事件。

不同的網站有不同的實作需求。某些維度和事件可在不同網站之間共用。舉例來說，電子郵件註冊可以在多個網站上採用相同事件，觸發相同的自訂事件。其他維度則可能為網站專用。例如，您只有一個網站可讓用戶變更個人檔案圖片，那麼這項自訂事件只能在可提供支援的網站上實作。

請務必確認不重複維度和量度的數量在單一全域報告套裝中適用。如果您發現不重複維度或量度數量過多，請檢查每項實作中的每個維度，因為當中可能存在對業務的成功不具關鍵性的重疊項目和維度。建議一併使用[分類](/help/components/classifications/c-classifications.md)功能。例如，請根據「產品」維度建立「產品名稱」分類，而不擷取 eVar5 中的「產品名稱」。任何相依的虛擬報告套裝都能自動使用來源報告套裝中的分類功能。

>[!TIP]
>
>由於我們推出了[組織](/help/analyze/analysis-workspace/curate-share/curate.md)功能，您現在可以根據各個 VRS 變更指定維度或量度的名稱。

### 區段的細微差別

基本層級的虛擬報告套裝單純是套用至報告套裝的區段。以造訪和訪客為依據的維度可提供非直覺式的報表結果。

舉例來說，您有 A 和 B 兩個網站，兩者都會將資料傳送至全域報告套裝。有些訪客不可避免地會在 A 網站和 B 網站之間移動，而這項在不同網站之間的移動會顯示在全域報告套裝的路徑中。如果您為網站 A 和 B 建立虛擬報告套裝，從網站 A 開始並在網站 B 結束的造訪不會在 VRS B 中顯示登入頁面，因為此次造訪的登入頁面始於網站 A，該造訪是從虛擬報告套裝中區分出來的。

### 貨幣轉換

虛擬報告套裝無法針對報告套裝所設貨幣以外的不同貨幣產生資料。Adobe Analytics 允許您在執行報表時轉換貨幣，但匯率是以當日為準 (即使歷史資料亦同)。

如果您的組織僅以一種貨幣進行分析，這項設定並不會造成問題。不過，如果您有重要業務需要不同地區的團隊以各自的當地貨幣來檢視收益，建議使用多套裝標記。

### 資料饋送

資料摘要無法使用虛擬報告套裝。不過，您可以從全域報告套裝接收資料摘要後，再加以區分。

資料摘要可讓您以個別點擊層級接收所有 Adobe Analytics 的每日或每小時匯出資料。資料摘要無法在傳送給您之前預先分段，因此您只能接收全域報告套裝的資料摘要。如果您的組織亟需針對品牌、屬性、地區或其他精細層級取得個別資料摘要，建議使用多套裝標記。

### 合作夥伴帳戶的 Data Connector

某些 Adobe Analytics 中的 Adobe 合作夥伴整合功能限制為每個報告套裝一個合作夥伴帳戶。某些組織可能需要多個合作夥伴帳戶才能進行相同的整合。

舉例來說，每個報告套裝僅允許使用一個 Google DCM。許多公司都有多個 DCM 帳戶，以便讓不同品牌、業務單位和地區彼此獨立管理各自的顯示廣告。整合無法在虛擬報告套裝中設定。如果您的多個帳戶都有相依的 Data Connector，建議使用多套裝標記。

### 摘要資料來源

摘要資料來源可讓您以報告套裝層級將彙總的量度匯入至 Adobe Analytics。由於摘要資料來源的上傳中含有彙總量度而&#x200B;*沒有訪客 ID*，因此在[!UICONTROL 造訪]和[!UICONTROL 訪客]容器中無法分段。由於 VRS 是透過區段來運作，如果區段是使用「造訪」或「訪客」容器建立，則使用摘要資料來源匯入的資料將不適用於虛擬報表套裝。

如果使用「點擊」容器，且該「點擊」容器已設定包含資料來源資訊的規則條件，則虛擬報表套裝中會顯示摘要資料來源。

>[!TIP]
>
>完整的資料來源處理可支援分段，且可用於虛擬報告套裝。

## 決定使用 VRS 時的依循步驟

如果您選擇移除次要伺服器呼叫，打算改用虛擬報告套裝：

1. 建立與子報告套裝資料相符的虛擬報告套裝。在自訂維度上設定區段，藉此在不同網站之間區隔您的網站。
   * 如果您從目前已完成多套裝標記的實作項目進行移轉，請先比較虛擬報告套裝的區段與現有的子報告套裝。在將用戶移至虛擬報告套裝之前，請先確認資料可互相比較。
   * 如需參考最佳做法，建議您使用[區段堆疊](/help/components/segmentation/segmentation-workflow/seg-build.md)，以便在同一位置編輯區段，並將區段套用至所有相依的虛擬報告套裝。
   * 如果您希望維持虛擬報告套裝彼此更加互斥，請使用點擊容器。
2. 在您確認虛擬報告套裝已正確設定後，請從實作項目中移除次要報告套裝 ID。如何移除次要報告套裝：
   * 在Adobe Experience Platform資料收集內的Adobe Analytics分機中，按一下您不想再使用的任何報告套件旁邊的「x」。
   * 在舊的 JavaScript 實作項目中，找到 `s.account` 變數並移除您不想再使用的任何報告套裝 ID。
   * 在所有情況下，僅需保留您的全域/父項報告套裝 ID，以便收集網站和應用程式的資料。
   * 導覽至管理 > 報告套裝，並隱藏任何不再使用的次要報告套裝。
