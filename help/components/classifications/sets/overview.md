---
title: 分類集概觀
description: 了解如何使用分類集來管理分類資料。了解分類集與舊版分類的區別。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: d5e1432569516d13d2de30a2cb30cebb067ab783
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 100%

---

# 分類集概觀

分類集會提供管理分類和規則的單一介面。此工作流程將在[»報告套裝設定](/help/admin/tools/manage-rs/report-suites-admin.md)中建立分類的功能與[分類匯入工具](/help/components/classifications/sets/set-manager.md)結合。結果是提供一個直覺易用的介面，可用來建立和管理分類資料。


## 分類集與舊版分類

分類集與舊版分類的主要區別在於，分類集將所有功能合併於一個介面中，而舊版分類則依賴三個介面。

### 舊版分類

![舊版分類](/help/components/classifications/sets/assets/classifications-legacy.svg)

在舊版分類中，分類![結構描述](/help/assets/icons2/Schema.svg) (例如流量、轉換、行銷管道等) 各自擁有自己的維度 (索引鍵![索引鍵](/help/assets/icons2/Key.svg))。您將這些分類定義為[報告套裝設定](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)的一部分。

您在規則集內將規則 ![BidRule](/help/assets/icons/BidRule.svg) 分開定義，作為[分類規則產生器](/help/components/classifications/crb/classification-rule-builder.md)介面的一部分。在該介面中，您將規則集與一個或多個報告套裝關聯。

您使用[分類匯入工具](/help/components/classifications/importer/c-working-with-saint.md)下載一個範本![文件片段](/help/assets/icons/DocumentFragment.svg)、將分類匯入![上傳至雲端](/help/assets/icons/UploadToCloud.svg)，或將分類從報告套裝 - 索引鍵 (資料集) 組合中匯出![下載](/help/assets/icons/Download.svg)。



### 分類集

![分類集](./assets/classifications-sets.svg)

分類集將所有舊版分類介面合併為一個。每個分類集定義：

* 一個或多個訂閱，這是您想要分類的報告套裝![資料](/help/assets/icons2/Data.svg)和維度![索引鍵](/help/assets/icons2/Key.svg) (索引鍵) 的組合。如果您想依據產品 SKU 來分類產品，您可以定義所有包含適用產品 SKU 維度的報告套裝。而且，您不需要像在舊版分類介面中那樣，複製報告套裝之間的分類。
* 該索引鍵的分類![結構描述](/help/assets/icons2/Schema.svg) (結構描述) 清單。例如，對於產品分類，您可以指定類別、顏色、大小、性別等。您定義分類之後，便可以下載範本![文件片段](/help/assets/icons/DocumentFragment.svg)、上傳![上傳至雲端](/help/assets/icons/UploadToCloud.svg)分類資料、下載![下載](/help/assets/icons/Download.svg)分類資料等。
* 支援分類的一個或多個規則 ![BidRule](/help/assets/icons/BidRule.svg)。


若要從 Adobe Analytics 介面的&#x200B;**[!UICONTROL 「元件」]**&#x200B;功能表中存取&#x200B;**[!UICONTROL 分類集]**，您必須是產品管理員，或屬於包含權限項目[!UICONTROL 「報告套裝工具」]>[!UICONTROL 「分類」]的產品輪廓。請注意，您可從&#x200B;**[!UICONTROL 「管理員」]**&#x200B;功能表存取舊版分類管理介面。

分類集包含三個主要功能區域：

* [**[!UICONTROL 分類集]**](set-manager.md)：建立、編輯和刪除分類集。
* [**[!UICONTROL 工作]**](job-manager.md)：查看分類集工作的狀態。
* [**[!UICONTROL 合併]**](consolidations/manage.md)：將多個分類集合併為單一分類集。


## 工作流程

分類集的工作流程通常包括以下步驟：

1. 考慮您要為哪些報告套裝和維度組合建立分類集。例如，您可以定義一個產品分類集，並套用至您想要對產品進行更詳細分類的任何報告套裝。例如，像類別和顏色等詳細資料。
1. [建立分類集](/help/components/classifications/sets/create.md)，使用一個或多個報告套裝的訂閱，以及用來識別產品的主要維度組合。例如：

   | 報告套裝 | 主要維度 |
   |---|---|
   | 報告套裝 1 | 產品 ID |
   | 報告套裝 2 | 產品 SKU |

1. 將您所識別的[分類增加](/help/components/classifications/sets/manage/schema.md#add)到分類集結構描述中。例如：

   | 分類名稱 | 身分識別名稱 |
   |---|---|
   | 類別 | 類別 |
   | 顏色 | 顏色 |

1. 手動建立一個包含分類資料的檔案。[使用範本](/help/components/classifications/sets/manage/schema.md#template)以確保您的檔案使用支援的[檔案格式](data-files.md#classification-set-file-formats)和欄。然後將資料新增到範本檔案中。

   或者，您可以直接從產品目錄中匯出資料，使用[支援的檔案格式](data-files.md#classification-set-file-formats)而且其欄也與範本相符。例如，一個 CSV 檔案，如下所示：

   ```
   Key,Category,Color
   Adobe Nike Tech Fleece Full-Zip Hoodie - Men's,Men,Black
   Adobe Nike Tech Fleece Full-Zip Hoodie - Women's,Women,Black
   Men's North Face Adobe Jacket,Men,Black
   Nike Air Hybrid 2 Golf Bag,Equipment,Blue
   STITCH&reg; Ultimate Garment Bag,Equipment,Brown
   Adobe Analytics Training Tee - Navy,Men,Navy
   AirPods Pro 2,Electronics,White
   Adobe Analytics Training Tee - Green,Men,Green
   Women's North Face Adobe Jacket,Women,Blue
   Adobe Analytics Training Tee - Grey,Men,Gray
   Adobe Analytics One Million Views - Grey,Equipment,Grey
   Adobe and MGM Tee - White,Women,White
   Adobe and MGM Tee - Charcoal,Women,Charcoal
   ```

   在分類資料檔案中，您使用 `Key` 來參照每個報告套裝的關鍵維度 (例如：**[!UICONTROL 產品 ID]**&#x200B;和&#x200B;**[!UICONTROL 產品 SKU]**)。您使用&#x200B;**[!UICONTROL 分類名稱]**&#x200B;來參照每個分類 (例如 `Category` 或 `Color`)。

1. [上傳](/help/components/classifications/sets/manage/schema.md#upload)包含分類資料的檔案至分類集結構描述中。

1. 設定[規則](manage/rules.md)以自動分類傳入的資料和過去的資料。

1. 透過使用雲端位置將產品目錄更新[自動化](/help/components/classifications/sets/manage/schema.md#automate)，以便反映在分類資料中。

1. [下載](/help/components/classifications/sets/manage/schema.md#download)您的分類資料以驗證內容。

1. [檢查工作歷史記錄](/help/components/classifications/sets/job-manager.md)以查看您在分類上的操作結果 (上傳、下載、範本等)。
1. 如果您有多個相似的分類集，這是由於從舊版分類功能的遷移結果，請[整合](consolidations/manage.md)這些分類集。



## 改善

隨著分類集發布的後端架構包含幾項改進：

* 減少處理時間 (從 72 小時縮短為 24 小時)。
* 重新設計用於管理分類的使用者介面。
* 透過[適用於分類資料的 Adobe Analytics 來源連接器](https://experienceleague.adobe.com/tw/en/docs/experience-platform/sources/connectors/adobe-applications/classifications)，在 Adobe Experience Platform 中使用分類資料的選項。

隨著分類集發布的後端架構也包含幾項變更：

* 當使用瀏覽器或自動化匯入時，**[!UICONTROL 衝突時覆蓋]**&#x200B;一定會啟用。
* 使用瀏覽器或自動匯入時，不再支援匯入後立即匯出的選項。匯出必須單獨啟動。
* Analytics 2.0 `GetDimensions`API 端點現在傳回字串識別碼而非數值識別碼來表示分類。數值識別碼仍然可以使用，但建議盡可能使用新的字串識別碼。可以使用 `?expansion=hidden` 查詢字串參數擷取數值識別碼。

>[!IMPORTANT]
>
>分類集的效能主要取決於包含資料的唯一關鍵值數量。當您擁有包含大量唯一值的變數時，請小心處理。特別是當您將來自多個報告套裝和維度的這些變數合併為單一分類集時。

## 限制

* 分類集尚不支援規則。在[舊版規則產生器](/help/components/classifications/crb/classification-rule-builder.md)功能未停止使用之前，規則功能已加入到分類集介面中。
* 舊版分類規則和設定無法遷移至分類集。在舊版分類功能未停止使用之前，已將遷移公用程式加入至分類集介面。
