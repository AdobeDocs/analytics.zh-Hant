---
title: 「分類設定」概觀
description: 瞭解如何使用分類設定來管理分類資料。 瞭解分類設定與舊版分類的差異。
exl-id: a139b298-1188-42ce-b52f-c71e0ff7c4e3
feature: Classifications
source-git-commit: 5256319752fb6521ef86c1dde9d3624689879ecb
workflow-type: tm+mt
source-wordcount: '950'
ht-degree: 9%

---

# 分類集概觀

分類集會提供管理分類和規則的單一介面。此工作流程會將在報告套裝設定中建立的分類與[分類匯入工具](/help/components/classifications/sets/manage/set-manager.md)結合。 如此將可透過單一直覺式介面建立和管理分類資料。


## 「分類設定」與「舊版分類」

分類設定和舊版分類的主要差異在於，分類設定將所有功能結合在一個介面中，而舊版分類需仰賴三個介面。

### 舊版分類

![舊分類](/help/components/classifications/sets/assets/classifications-legacy.svg)

在舊版分類中，分類![結構描述](/help/assets/icons2/Schema.svg) （例如流量、轉換、行銷管道等）都有各自的維度（索引鍵![索引鍵](/help/assets/icons2/Key.svg)）。 您將這些分類定義為[報表套裝設定](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/conversion-classifications.md)的一部分。

您已在規則集中個別定義規則![BidRule](/help/assets/icons/BidRule.svg)，作為[分類規則產生器](/help/components/classifications/crb/classification-rule-builder.md)介面的一部分。 在該介面中，您會將規則集與一個或多個報表套裝相關聯。

您使用[分類匯入工具](/help/components/classifications/importer/c-working-with-saint.md)下載範本![DocumentFragment](/help/assets/icons/DocumentFragment.svg)、將![UploadToCloud](/help/assets/icons/UploadToCloud.svg)分類匯入或匯出![下載](/help/assets/icons/Download.svg)分類(從報表套裝 — 索引鍵（資料集）組合)。



### 分類集

![分類設定](./assets/classifications-sets.svg)

分類設定將所有舊有的分類介面結合為一個。 每個分類設定都會定義：

* 您要分類的一或多個訂閱，是報表套裝![資料](/help/assets/icons2/Data.svg)和維度![索引鍵](/help/assets/icons2/Key.svg) （索引鍵）的組合。 如果您想要根據產品SKU來分類產品，可以使用適用的產品SKU維度來定義所有報表套裝。 您也不必像舊版分類介面那樣，跨報表套裝復寫分類。
* 索引鍵的分類![結構描述](/help/assets/icons2/Schema.svg) （結構描述）清單。 例如，對於產品分類，您可以指定類別、顏色、大小、性別等。 定義分類後，您可以下載範本![DocumentFragment](/help/assets/icons/DocumentFragment.svg)、上傳![UploadToCloud](/help/assets/icons/UploadToCloud.svg)分類資料、下載![下載](/help/assets/icons/Download.svg)分類資料等。
* 一或多個規則![BidRule](/help/assets/icons/BidRule.svg)可支援分類。


若要從Adobe Analytics介面的&#x200B;**[!UICONTROL 元件]**&#x200B;功能表存取&#x200B;**[!UICONTROL 分類集]**，您必須是產品管理員或屬於包含許可權專案[!UICONTROL 報告套裝工具] > [!UICONTROL 分類]的產品設定檔。 請注意，舊版分類管理介面可從&#x200B;**[!UICONTROL 管理員]**&#x200B;功能表取得。

「分類設定」包含三個功能區域：

* [**[!UICONTROL 分類設定]**](manage/set-manager.md)：建立、編輯和刪除分類設定。
* [**[!UICONTROL 工作]**](job-manager.md)：檢視分類集工作的狀態。
* [**[!UICONTROL 合併]**](consolidations/manage.md)：將多個分類集合併為單一分類集。


## 工作流程

分類集的工作流程通常涉及以下步驟：

1. 考慮您要為哪些報表套裝和維度組合建立分類集。 例如，可定義您針對任何要分類產品（包含更多詳細資訊）的報告套裝所建立的產品分類集。 例如，類別和顏色等詳細資訊。
1. [建立一個分類集](/help/components/classifications/sets/manage/create.md)，其中包含一或多個可識別產品的報表套裝和索引鍵維度組合的訂閱。 例如：

   | 報告套裝 | 主要維度 |
   |---|---|
   | 報告套裝1 | 產品 ID |
   | 報告套裝2 | 產品SKU |

1. [將已識別的分類](/help/components/classifications/sets/manage/schema.md#add)新增至分類集結構描述。 例如：

   | 分類名稱 | 身分識別名稱 |
   |---|---|
   | 類別 | 類別 |
   | 色彩 | 顏色 |

1. 手動建立包含分類資料的檔案。 [使用範本](/help/components/classifications/sets/manage/schema.md#template)，以確保使用檔案的[支援檔案格式](data-files.md#classification-set-file-formats)和資料行。 然後將資料新增至範本檔案。

   或者，您可以直接從[支援的檔案格式](data-files.md#classification-set-file-formats)產品目錄中匯出資料，其欄需符合範本。 例如，CSV檔案，例如：

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

   在分類資料檔案中，您使用&#x200B;**[!UICONTROL 參照每個報表套裝的關鍵維度（例如：]**&#x200B;產品ID **[!UICONTROL 和]**&#x200B;產品SKU`Key`）。 而且您可以使用&#x200B;**[!UICONTROL 分類名稱]** （例如`Category`或`Color`）來參照每個分類。

1. [將包含分類資料的檔案上傳](/help/components/classifications/sets/manage/schema.md#upload)至分類設定結構描述。

1. 設定[規則](manage/rules.md)以自動分類過去傳入的資料和資料。

1. [使用雲端位置，自動處理](/help/components/classifications/sets/manage/schema.md#automate)更新產品目錄的程式，您要看到這些更新反映在分類資料中。

1. [下載](/help/components/classifications/sets/manage/schema.md#download)您的分類資料以驗證內容。

1. [檢查工作歷史記錄](/help/components/classifications/sets/job-manager.md)以檢視分類上動作（上傳、下載、範本等）的結果。
1. 如果您因從舊版分類功能移轉而擁有多個類似的分類設定，請[合併](consolidations/manage.md)這些分類設定。



## 改善

隨分類集發行的後端架構包含幾項改善：

* 縮短處理時間（從72小時縮短至24小時）。
* 重新設計的使用者介面以管理分類。
* 透過[Adobe Experience Platform來源聯結器將分類資料用於Adobe Analytics中的選項](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/sources/connectors/adobe-applications/classifications)。

隨分類集發行的後端架構也包含幾項變更：

* 使用瀏覽器或自動匯入時，一律啟用&#x200B;**[!UICONTROL 在衝突時覆寫]**。
* 使用瀏覽器或自動匯入時，不再支援匯入後立即匯出的選項。匯出必須單獨啟動。
* Analytics 2.0 `GetDimensions` API端點現在會傳回分類的字串識別碼，而非數值識別碼。 數值識別碼仍可使用，但建議儘可能使用新的字串識別碼。 可以使用 `?expansion=hidden` 查詢字串參數擷取數值識別碼。

>[!IMPORTANT]
>
>分類集的效能主要取決於包含資料的唯一關鍵值數量。當變數包含大量不重複值時，請務必小心。 尤其當您從多個報告套裝和維度中組合這類變數至單一分類集。

## 限制

* 分類設定尚不支援規則。 在[舊版規則產生器](/help/components/classifications/crb/classification-rule-builder.md)功能無法使用之前，已將規則功能新增到分類集介面。
* 舊版分類規則和設定無法移轉至分類設定。 在舊版分類功能無法使用之前，已將移轉公用程式新增到分類設定介面。
