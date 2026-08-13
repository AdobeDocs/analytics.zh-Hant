---
description: 您可以使用瀏覽器匯入（上傳）分類資料。 這種方法限制您的分類資料上傳只能上傳單一的報表套裝
title: 瀏覽器匯入
feature: Classifications
exl-id: 5bef1f6d-9b27-464d-8343-472f300a7437
TQID: https://experienceleague.adobe.com/iFVW-d9C12dj6TXnUlA3-zVF0oBAWpJwg1JK8LqzF-s
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 52%

---

# 瀏覽器匯入（舊版）

{{classification-importer-deprecation}}

您可以使用瀏覽器匯入（上傳）分類資料。 這種方法限制您的分類資料上傳只能上傳單一的報表套裝

## 瀏覽器匯入 {#concept_314FB3D5FD5A439B9CFEDE37A3337BA7}

您可以使用瀏覽器匯入（上傳）分類資料。 這種方法限制您的分類資料上傳只能上傳單一的報表套裝

**[!UICONTROL 管理員]** > **[!UICONTROL 分類匯入工具]**

## 分類瀏覽器匯入 - 欄位說明 {#section_F628C47081DA4026A4D30E3D3454B1DA}

| 元素 | 說明 |
| --- | --- |
| 選取報表套裝 | 您要匯入分類資料的報表套裝。 匯入資料檔案必須與報表套裝中資料集的格式相符。 |
| 要分類的資料集 | 要接收分類的資料集。 下拉式清單含有報表套裝中所有已針對分類設定的報告。 |
| 選取要匯入的檔案 | 可讓您瀏覽以找出您要上傳的匯入資料檔案。  注意：上傳檔案大小限制是 1 MB。 |
| 發生衝突時覆寫資料 | 自動覆寫與匯入資料衝突的現有資料。<br>**重要**：此選項不適用於已啟用「新分類架構」的報表套裝。 |
| 匯入完成後自動下載分類檔案 | 自動下載以Tab分隔的檔案，該檔案代表具有新上傳之分類資料的資料集。 如果匯入建立任何唯一ID，或發生任何錯誤，Adobe會自動為您產生此檔案。<br>**重要**：此選項不適用於已啟用「新分類架構」的報表套裝。 |


## 透過瀏覽器匯入分類 {#task_D7D51CB6FB35437AB68599B1B23FEAC1}

1. 按一下&#x200B;**[!UICONTROL 「管理員]** > **[!UICONTROL 分類匯入工具」]**。
1. 按一下&#x200B;**[!UICONTROL 「匯入檔案」]**。
1. 設定&#x200B;**[!UICONTROL 瀏覽器匯入]**&#x200B;欄位。
1. 按一下&#x200B;**[!UICONTROL 「匯入檔案」]**。
1. 觀察狀態視窗中的處理訊息。
1. (有條件) 若您選取「**[!UICONTROL 上傳完成時自動下載分類檔案]**」，則需指定處理完成時要將產生的檔案儲存於何處。 請注意，此選項不適用於已啟用「新分類架構」的報表套裝。

>成功的匯入會立即在匯出中顯示適當的變更。 不過，使用瀏覽器匯入時，報表中的資料變更需時長達四小時，使用FTP匯入時，則需時長達二十四小時。
