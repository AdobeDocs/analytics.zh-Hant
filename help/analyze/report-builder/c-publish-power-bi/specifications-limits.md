---
description: 'null'
title: 限制與規格
uuid: 6717b6ea-7e01-49b8-8f6e-fb733a03b687
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 100%

---


# 限制與規格

## Power BI 發佈限制 {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
> 這些限制僅適用於「以 Power BI 資料集表格形式發佈 Report Builder 請求」選項。

* 每個活頁簿最多可將 100 個 Report Builder 請求匯出至 Power BI。
* 達到第 101 個請求時，排程程序將會停止匯出請求。
* 系統只會將每個 Report Builder 請求的前 10,000 列 Analytics 資料傳送至 Power BI。剩餘的資料列將會被忽略。

## 在發佈至 Power BI 後編輯 Report Builder 請求 {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
> 此規格可套用至「以 Power BI 資料集表格形式發佈所有 Report Builder 請求」選項和「在活頁簿中以 Power BI 資料集表格形式發佈所有格式化表格」選項。

在發佈至 Power BI 後編輯 Report Builder 請求可能會造成問題。

* **案例 1**：您將活頁簿發佈至 Power BI，並根據其中的資料建立視覺效果。接著，您對活頁簿作出變更，並導致其參考之資料集的其中一欄消失。然後您重新發佈活頁簿。這樣會中斷 Power BI 中的視覺效果。

   **以下是視覺效果「將會」中斷的範例：**

   1. 在 Report Builder 中，使用「頁面」維度和「頁面檢視」量度建立含有一個請求的活頁簿。
   1. [排程此請求](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)以發佈至 Power BI。
   1. 在 Power BI 中，針對「頁面」與「頁面檢視」建立視覺效果。
   1. 現在，移除請求中的「頁面檢視」以編輯活頁簿。
   1. 使用更新的活頁簿編輯排程，然後將請求重新發佈至 Power BI。
   1. 將新的活頁簿傳送至 Power BI 後

      1. 確認其覆寫您第一次發佈時所建立的現有資料集。
      1. 確認 page_1 表格已正確更新「頁面」欄與「造訪」欄。
      1. 確認視覺效果已中斷，因為其參考已不存在於 page_1 表格中的「頁面檢視」欄。

   **以下是視覺效果「不會」中斷的範例：**

   1. 在 Report Builder 中，使用「頁面」維度和「頁面檢視」量度建立含有一個請求的活頁簿。
   1. [排程此請求](/help/analyze/report-builder/whats-new-arb.md#rb-5-5-section)以發佈至 Power BI。
   1. 在 Power BI 中，針對「頁面」與「頁面檢視」建立視覺效果。
   1. 現在，在 Report Builder 中編輯活頁簿，新增「造訪」量度，同時保留「頁面」與「頁面檢視」。
   1. 使用更新的活頁簿編輯排程，然後將請求重新發佈至 Power BI。
   1. 將新的活頁簿傳送至 Power BI 後

      1. 確認其覆寫您第一次發佈時所建立的現有資料集。
      1. 確認 page_1 表格已正確更新「頁面」、「頁面檢視」及「造訪」欄。
      1. 確認視覺效果持續正常運作，因為其參考仍存在於 page_1 表格中的其中兩欄。


* **案例 2**：您將活頁簿的某個區段釘選至 Power BI 中的控制面板，隨後又將該釘選區段 (例如圖表或表格) 從活頁簿中移除。這樣將會中斷視覺效果。

## 變更 Power BI 報表的名稱 {#section_2E7893A78B914EBFACB2B08CBD9E472E}

除了空格會替換成底線字元之外，名稱依預設會填入活頁簿的檔名 (沒有 .xlsx 副檔名)。

請記住：

* 標籤不能是字母和數字的組合，因為系統可能會將其誤認為列或欄的位址。例如，A100 不能作為標籤，因為其為活頁簿中儲存格的位址。
* 以下字元為無效的標籤字元：「#」、「@」、「!」、「$」、「^」、「&amp;」、「*」、「`」、「~」、「 」。這些字元將會替換成底線字元。
* 輸入無效的名稱時，畫面將會顯示警告訊息，並建議自動產生的名稱。如果您按一下&#x200B;**[!UICONTROL 「是」]**，系統將會使用此名稱。如果您按一下&#x200B;**[!UICONTROL 「否」]**，「進階精靈」使用者介面將會讓您輸入新名稱。

