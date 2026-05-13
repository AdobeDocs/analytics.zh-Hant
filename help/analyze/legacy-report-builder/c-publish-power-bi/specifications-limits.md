---
description: 使用 Report Builder 和 Microsoft Power BI 時的限制。
title: 限制與規格
feature: Report Builder
role: User, Admin
exl-id: 4bbeec5b-64bc-4285-9f13-33b223b88834
TQID: https://experienceleague.adobe.com/L3R3ufcclrTpw-fKoFLD8Y-v56rTm4tXlXqjaTdmdoQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: c153fd90-23e1-4614-81d3-3cc7571227f7id: f73667dc-d296-4875-8975-ac3fdc3adc42
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 631
ht-degree: 29%

---

# 限制與規格

{{legacy-arb}}

## Power BI 發佈限制 {#section_D4BDD70B20F94A0FAE53531CA528AE42}

>[!NOTE]
>
>這些限制僅適用於「以 Power BI 資料集表格形式發佈 Report Builder 請求」選項。

* 每個活頁簿最多可以將100個Report Builder請求匯出至Power BI。
* 當達到第101個請求時，排程程式將停止匯出請求。
* 根據Report Builder請求，只有前10,000列Analytics資料會傳送至Power BI。 其餘的列將被忽略。

## 在發佈至 Power BI 後編輯 Report Builder 請求 {#section_6989E74F68DD43F08D37C36B6777DB50}

>[!NOTE]
>
>此規格適用於「以 Power BI 資料集表格形式發佈所有 Report Builder 請求」選項和「將活頁簿中所有格式化表格以 Power BI 資料集表格形式發佈」選項。

在將Report Builder請求發佈至Power BI後進行編輯可能會造成問題。

* **案例 1**：您將活頁簿發佈至 Power BI，並根據其中的資料建立視覺效果。 接著，您對活頁簿進行變更，導致其參考的資料集其中一個欄消失。 然後再重新發佈。 這會中斷Power BI中的視覺效果。

  **以下是視覺效果「將會」中斷的範例：**

   1. 在Report Builder中，使用「頁面」維度和「頁面檢視」量度，建立含有一個請求的活頁簿。
   2. 排程此請求以發佈至 Power BI。
   3. 在Power BI中，建立「頁面」和「頁面檢視」的視覺效果。
   4. 現在可從請求中移除「頁面檢視」 ，以編輯活頁簿。
   5. 使用更新的活頁簿編輯排程，然後重新發佈請求到Power BI。
   6. 新活頁簿傳送至Power BI後

      1. 確認它覆寫了您首次發佈時建立的現有資料集。
      2. 確認page_1表格已正確更新「頁面」和「造訪」欄。
      3. 確認您的視覺效果已失效，因為它參考了page_1表格中不再存在的「頁面檢視」欄。

  **以下是視覺效果「不會」中斷的範例：**

   1. 在Report Builder中，使用「頁面」維度和「頁面檢視」量度，建立含有一個請求的活頁簿。
   2. 排程此請求以發佈至 Power BI。
   3. 在Power BI中，建立「頁面」和「頁面檢視」的視覺效果。
   4. 現在編輯Report Builder中的活頁簿，在保留「頁面」和「頁面檢視」的同時新增「造訪」量度。
   5. 使用更新的活頁簿編輯排程，然後重新發佈請求到Power BI。
   6. 新活頁簿傳送至Power BI後

      1. 確認它覆寫了您首次發佈時建立的現有資料集。
      2. 確認page_1表格已正確更新，「頁面」、「頁面檢視」和「造訪」欄。
      3. 確認您的視覺效果可繼續正常運作，因為其參考的兩欄仍存在於page_1表格中。

* **案例 2**：您將活頁簿的某個區段釘選至 Power BI 中的儀表板，隨後又將該釘選區段 (例如圖表或表格) 從活頁簿中移除。 這將會破壞視覺效果。

## 變更 Power BI 報表的名稱 {#section_2E7893A78B914EBFACB2B08CBD9E472E}

預設會從活頁簿檔案名稱填入名稱（不含.xlsx副檔名），但空格會以底線字元取代。

請記住：

* 標籤不能是字母和數字的組合，可能被誤認為列和欄位址。 例如，A100不能是標籤，因為它是工作表中儲存格的位址。
* 以下字元為無效的標籤字元：`'#', '@', '!', '$', '^', '&', '&#42;', '`&#39; 和 `'~', ' '`。 這些字元將會替換成底線字元。
* 輸入無效名稱時，系統會顯示警告訊息，建議自動產生名稱。 如果您按一下&#x200B;**[!UICONTROL 是]**，將會使用此名稱。 如果您按一下&#x200B;**[!UICONTROL 否]**，進階精靈UI會讓您輸入新名稱。
