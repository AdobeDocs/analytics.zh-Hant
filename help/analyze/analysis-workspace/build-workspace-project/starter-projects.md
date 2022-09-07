---
description: 根據標準或自訂範本建立 Workspace 專案。
title: 範本
feature: Workspace Basics
role: User, Admin
exl-id: 751399fe-6d4f-47cc-8827-82c992079b52
source-git-commit: be913fb9bae7954864b180490364c275c7bf7f15
workflow-type: tm+mt
source-wordcount: '1313'
ht-degree: 93%

---

# 範本

您可以選擇從以下來源建立專案：

* **空白專案 (預設)**：如需操作說明，請參閱[建立 Analysis Workspace 專案](/help/analyze/analysis-workspace/home.md)。
* **標準範本**：這些範本是由 Adobe 建立並隨產品提供。
* **自訂範本**：這些範本可由具有管理員權限的使用者或非管理員建立、共用或刪除，但前提是他們已在 Admin Console 中獲得 [!UICONTROL Analysis Workspace：儲存為範本]權限。[進一步了解...](https://experienceleague.adobe.com/docs/analytics/admin/admin-console/permissions/product-profile.html?lang=zh-Hant)

![](assets/start_modal.png)

## 建立自訂範本 {#create-custom-template}

擁有管理員權限的使用者可以將其建立的任何專案轉換為自訂範本。方法如下：

1. 開啟專案。
1. 前往&#x200B;**[!UICONTROL 「專案]** > **[!UICONTROL 另存為範本」]**。

   ![](assets/save_project_template.png)

   專案將以目前的專案名稱儲存，並於後方以括號加上「(範本)」一詞。管理員可以透過編輯範本來變更名稱。

   >[!NOTE]
   >
   >預設狀況下，您組織中的所有人都可以檢視專案範本。您可以透過套用標記的方式組織範本。(前往&#x200B;**[!UICONTROL 「專案]** > **[!UICONTROL 專案資訊和設定」]**&#x200B;即可編輯標記和說明)。

以下是有關建立及管理自訂範本的影片：

>[!VIDEO](https://video.tv.adobe.com/v/23231/?quality=12)

### 管理自訂範本 {#manage-custom-template}

| 動作 | 說明 |
|--- |--- |
| 編輯範本 | 可讓管理員透過變更資料來源、修改元件、視覺效果和日期範圍等方式編輯範本。若要編輯自訂範本，您可以<ul><li>開啟 Analysis Workspace 中的自訂範本清單、選取一個範本，然後按一下「編輯範本」，或</li><li>在 Analytics 中，導覽至「元件 > 專案」，然後篩選「範本」。按一下您想要編輯的範本名稱。</li></ul>**附註:** 視情況而定，您在編輯範本後有兩個選項:「儲存」、「另存新檔」。兩者的差異如下：<ul><li>**儲存**：會更新所有使用者的自訂範本。其他人從這個自訂範本建立專案時，就會看到您變更的內容。</li><li>**另存新檔**：會建立含有您變更內容的自訂範本副本。(「共用 > 共用專案」的選單項目停用時，您就可以得知目前處於編輯模式。)</li></ul> |
| 搜尋範本 | 在「自訂範本」對話方塊中，按一下「搜尋範本」。 |
| 將範本排序 | 您可以依字母順序、關聯性以及建立日期等將範本排序。在「自訂範本」對話方塊中，按一下「排序：」。 |
| 套用標記至範本 | 開啟範本，然後前往「專案 > 專案資訊和設定」。按一下「新增標記」。 |
| 修改範本說明 | 開啟範本，然後前往「專案 > 專案資訊和設定」。連按兩下說明並進行編輯。 |


## 標準範本

第一次開啟 Workspace 時，範本位於左側邊欄中。Analysis Workspace 範本涵蓋常見的使用案例。這些專案依據其所屬垂直產業而分組，並根據您選取的報表套裝，填入不同的維度、區段、量度和視覺效果。

您可照原樣使用這些預先填入的範本，或是依照您的需求據以調整 (例如透過新增或更換量度或視覺效果)，然後以新名稱儲存這些範本。

以下是有關 [Analysis Workspace 中的標準範本](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/analysis-workspace/analysis-workspace-basics/standard-templates-in-analysis-workspace.html?lang=zh-Hant)的教學影片 (2:46)

以下為可用的範本，以及可透過個別範本找到答案的問題.

### 培訓

這個標準範本會逐步引導您了解常用術語，以及在工作區中初次建立分析的步驟。 若新使用者的清單中沒有其他專案，這會顯示為「新增專案」模組中的標準範本，取代目前現有的範例專案。

以下是有關[!UICONTROL 訓練教學課程]範本的影片：

>[!VIDEO](https://video.tv.adobe.com/v/33773/?quality=12)

### 廣告

>[!IMPORTANT]
>
>您必須在 [Advertising Analytics](https://experienceleague.adobe.com/docs/analytics/integration/advertising-analytics/overview.html?lang=zh-Hant) 中啟用報表套裝，才可使用廣告範本。

* **付費搜尋引擎**：此範本可劃分廣告趨勢、廣告平台、關鍵字、帳戶、促銷活動等項目。

### 商務

* **Magento：行銷與商務**：此範本依行銷通路歸因來劃分電子商務轉換，並依搜尋關鍵字、登陸頁面、地理位置等條件提供深入分析。以下是有關 [Magento：行銷和商務範本](https://experienceleague.adobe.com/docs/analytics-learn/tutorials/integrations/magento/magento-analysis-workspace-template.html?lang=zh-Hant)的影片教學。

### 資料收集

* **ITP 影響**：了解 Apple 的 ITP 如何影響您的資料以及如何相應地調整報表。

### 媒體

* **內容使用**：我的忠實讀者是哪些人
* **造訪間隔 - 頻率 - 忠誠度**：哪一項內容最常被使用且吸引使用者？
* **串流媒體使用**：提供所有數位裝置上媒體使用的趨勢和排名在前的量度。 以下是有關串流媒體使用範本的影片：

   >[!VIDEO](https://video.tv.adobe.com/v/23901/?quality=12)

### 行動

>[!IMPORTANT]
>
>您必須在行動應用程式分析中啟用報表套裝，才可使用行動範本。

* **獲取：**&#x200B;了解行動裝置獲取連結的成效。
* **應用程式使用情形：**&#x200B;應用程式擁有多少使用者和首次啟動次數，以及平均工作階段時間長度為何？
* **歷程：**&#x200B;我的應用程式的顯著使用模式為何？
* **關鍵量度：**&#x200B;掌握您應用程式的關鍵量度。
* **位置：**&#x200B;包含可呈現位置資料的地圖。
* **傳送訊息：**&#x200B;著重於應用程式內及推播訊息的效能。
* **成效：**&#x200B;應用程式的成效如何，以及使用者在哪些階段遭遇問題？
* **保留率：**&#x200B;我的忠實使用者是哪些人，以及他們都進行什麼活動？

### 零售

* **促銷活動成效：**&#x200B;什麼促銷活動帶來的收入最高？
* **產品：**&#x200B;哪些產品成效最佳？

### Web

* **贏取：**&#x200B;為我的網站帶來最多流量的因素是什麼？
* **AEM 網站績效概觀：**&#x200B;我的 Adobe Experience Manager 網站的表現如何？
* **內容消耗：**&#x200B;使用者最常前往我網站的哪些位置？
* **保留率：**&#x200B;什麼類型的使用者可能成為我網站的忠實使用者？
* **技術：**&#x200B;使用者使用哪些技術來存取我的網站？

### 人物

此範本是根據「人物」量度建立，此量度是「不重複訪客」量度刪除重複項目後的版本。「人物」量度提供的是客戶利用多部裝置與品牌互動的頻率。此範本可讓您:

* 劃分美國/加拿大與世界其他地區的資料
* 並排比較「人員」和「獨特訪客」量度
* 請參閱「壓縮率」，此計算量度可計算「人物」量度相對於「不重複訪客」的百分比小得多少
* 比較客戶所使用的裝置類型總數
* 了解每人平均使用的裝置數
* 探索如何搭配「人物」量度使用區段堆疊
* 探索在您的環境中使用Experience CloudID如何增強「人員」量度的效益

### Journey IQ：Cross-Device Analytics 範本

<!--This content is mirrored in the CDA doc.-->

此範本可讓您了解重要的跨裝置效能資料。這個範本僅供可存取 [Cross-Device Analytics](https://experienceleague.adobe.com/docs/analytics/components/cda/overview.html?lang=zh-Hant) (CDA) 的客戶使用。

* **使用者身分識別**：顯示使用以 Cross-Device Analytics 為基礎之方法識別網站訪客的頻率。
* **衡量對象規模**：顯示「不重複裝置」與「人物」的比較。這兩個數字的比例稱為「跨裝置壓縮」，也就是此面板中顯示的計算量度。此轉換量度取決於多種因素：
   * **登入率**：登入您網站的使用者越多，Adobe 就能越有效跨裝置識別並結合訪客。登入率低的網站壓縮率也會很低。
   * **Experience Cloud ID 涵蓋範圍**：系統只會結合具有 ECID 的訪客。使用 ECID 造訪您網站的訪客比例較低，與壓縮率較低有關。
   * **使用多部裝置**：若您網站的訪客沒有使用多部裝置，壓縮率便會較低。
   * **報表詳細程度**：依日計算的壓縮率通常比依月或年計算的壓縮率還低。依個人在一天內使用多部裝置的機率，會比整個月的機率小。分段、篩選或使用劃分維度也可以顯示較低的壓縮率。
* **以人物為基礎的區段**：包含區段下拉式清單，可讓您檢視裝置特定資料。此面板鼓勵您試用區段，以便了解納入或排除裝置類型對報表有何影響。
* **分析跨裝置歷程**：根據裝置類型提供流量和流失報表。
* **跨裝置歸因**：結合 Journey IQ 和 Attribution IQ 的功能。
* **其他秘訣與技巧**：可協助您更順利使用 CDA 的實用主題。
