---
description: 「單頁存取次數」報表不應與 Ad Hoc Analysis 中的「單頁存取次數」量度混淆；前者會顯示您的網站訪客在進入後隨即退出，而未檢視任何其他頁面的頁面。
title: 單頁存取次數
topic: Reports
uuid: 5ca52be8-c7f5-464a-8a06-55e8271760b4
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 單頁存取次數

「單頁存取次數」報表不應與 Ad Hoc Analysis 中的「單頁存取次數」量度混淆；前者會顯示您的網站訪客在進入後隨即退出，而未檢視任何其他頁面的頁面。

此報告最常用於[!UICONTROL 頁面]報告的環境中，但也可在所有已啟用[!UICONTROL 路徑]的流量變數中檢視。您可以使用此報告來識別最不可能吸引訪客進一步瀏覽您的網站的登入頁面，或判斷單一頁面包含多少次瀏覽。這項資訊可讓您將內容最佳化，以降低這些頁面的退出率。

## 報告的屬性 {#section_2D30F939FE0648EF983DD7C1BAB1181B}

* 以[!UICONTROL 單次存取]作為量度，可提取[!UICONTROL 頁面]報告以擷取相同的報告。

* 我們將單頁瀏覽視為包含一個唯一值 (而非單一影像要求) 的瀏覽。

   * 在[頁面報告](/help/components/c-variables/dimensionslist/reports-pages.md)的環境中，在瀏覽中只能引發一個唯一頁面。
   * 在[網站區域報表](/help/components/c-variables/dimensionslist/reports-site-sections.md)的環境中，會在瀏覽中引發單一唯一網站區域。
   * 在[流量變數](/help/admin/admin/c-traffic-variables/traffic-var.md)的環境中，瀏覽會在單一唯一值引發時填入此報告。

* 單頁瀏覽可包含許多影像要求，只要報告環境中的變數包含單一唯一值。在第二個唯一值填入後，瀏覽即不再被視為單頁瀏覽。
* 我們將其視為一種路徑報告。[!UICONTROL 頁面]變數依預設會啟用路徑功能。但所有的流量變數也都具有此功能。是否可對其他流量變數啟用路徑功能，取決於您的合約。請洽詢組織的客戶經理，以取得詳細資訊。
* 此報告可使用搜尋篩選器尋找特定明細項目。
* 此報告可使用[趨勢](/help/components/c-variables/dimensionslist/reports-types.md)和[排名](/help/components/c-variables/dimensionslist/reports-types.md)格式。

* 此報告中無法使用劃分功能。
* [!UICONTROL 瀏覽]是此報告中唯一可用的量度。

