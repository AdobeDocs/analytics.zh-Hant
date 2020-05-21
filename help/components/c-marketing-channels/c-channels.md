---
description: 在行銷管道管理員中新增或啟用行銷管道。對於沒有行銷管道的報表套裝，自動設定可為您建立多個管道及其規則。您可視需要編輯預定義管道或建立自己的管道 (最多總共 25 個)。
subtopic: Marketing channels
title: 管理行銷管道
topic: Reports and analytics
uuid: 9d367bb6-a17b-49b8-9cd5-24fac35ae982
translation-type: ht
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 管理行銷管道

在行銷管道管理員中新增或啟用行銷管道。對於沒有行銷管道的報表套裝，自動設定可為您建立多個管道及其規則。您可視需要編輯預定義管道或建立自己的管道 (最多總共 25 個)。

以下是建立管道的指引：

* 透過設立所有管道的清單來提前計劃，以便將所有訪客點按歸入正確的管道類別。
* 一律包括[內部](/help/components/c-marketing-channels/c-faq.md)點按和[直接](/help/components/c-marketing-channels/c-faq.md)點按類別的管道。

[!UICONTROL 新增管道至「行銷管道」頁面，與在「行銷管道處理規則」頁面上建立規則是相互獨立的][](/help/components/c-marketing-channels/c-rules.md)。建立規則時，您會將規則與管道相關聯。

## 新增行銷管道 {#add-mktg-channels}

在行銷管道管理員中新增行銷管道。

>[!NOTE] 管道無法刪除。如果不想使用管道，則可停用或重新命名它，並保留以備將來之用。

1. 按一下&#x200B;**[!UICONTROL 「Analytics]** > **[!UICONTROL 管理]** > **[!UICONTROL 報表套裝」]**。
1. 在[!UICONTROL 「報告套裝管理員」]頁面上，選擇一個報告套裝。

   如果選擇多個報表套裝，請選擇一個範本，將範本設定複製到所選的報表套裝。

   請參閱[套用範本報表套裝設定至多個報表套裝](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。

1. 按一下&#x200B;**[!UICONTROL 「編輯設定]** > **[!UICONTROL 行銷管道]** > **[!UICONTROL 行銷管道管理員」]**。

   如果報表套裝尚未定義管道，則會顯示[自動設定](/help/components/c-marketing-channels/c-getting-started-mchannel.md)頁面。

1. 在[!UICONTROL 行銷管道管理員]頁面上，按一下&#x200B;**[!UICONTROL 「新增管道」]**。

   已定義 25 個管道時，此選項不可用。

1. 按一下&#x200B;**[!UICONTROL 「儲存」]**。
1. 若要設定管道規則，請按一下&#x200B;**[!UICONTROL 「行銷管道處理規則」]**。

   請參閱[建立行銷管道處理規則](/help/components/c-marketing-channels/c-rules.md)。

## 行銷管道管理員 - 介面定義 {#mktg-channel-mgr}

[!UICONTROL 行銷管道管理員]頁面的欄位定義。

| 欄位 | 定義 |
|--- |--- |
| 已啟用 | 啟用或停用該行銷管道。 |
| 管道名稱 | 行銷管道的友好名稱。 |
| 覆蓋上次接觸管道 | 可讓您選擇是否使用選取的管道覆蓋現有的永久性上次接觸管道。如果勾選此核取方塊，任何管道 (包括直接和內部) 都會覆蓋現有的上次接觸管道。產生的結果會將轉換歸屬於可能不值得該評價的管道。例如，若之前已透過免費搜尋管道獲得使用者，則此選項可確保直接管道不會接收用於轉換的評價。 |
| 管道劃分 | 允許您依該值劃分管道。建立[行銷管道分類](/help/components/c-marketing-channels/classifictions-mchannel.md)時，您可新增可能的管道劃分 (子管道)。 |
| 類型 | 指定使用者前往您網站的方式。您可選擇「線上」或「離線」。對於透過搜尋引擎或電子郵件促銷活動到來的訪客，您可使用「線上」管道。「離線」管道適用於透過報章廣告或雜誌廣告找到您網站的訪客。離線管道通常包括從報告資料來源匯入的資料。請參閱 [Data Sources](https://docs.adobe.com/content/help/zh-Hant/analytics/import/data-sources/datasrc-home.html)。請參閱[新增離線資料](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。 |
| 色彩 | 與該行銷管道相關的色彩。該色彩代表行銷管道報表中的管道。 |

## 定義管道

報表中要能顯示管道和管道資料，首先須建立管道和處理資料的基本規則。您亦可建立相關管道的成本和預算額，並指定所需的訪客參與有效期。報表設定工作在「管理工具」中執行。

將渠道想像為瀏覽的容器，而規則是為適當的容器指派瀏覽。

![](assets/buckets_2.png)

Adobe 在[自動設定](/help/components/c-marketing-channels/c-getting-started-mchannel.md)期間提供數個預定義管道，您可視需求加以編輯。

>[!NOTE]
>
>Adobe 建議在您能作為測試範本使用的報表套裝中設定報表。您可使用範本將管道和規則設定總體套用至一個或多個生產報表套裝。
>
>請參閱[套用範本報表套裝設定至多個報表套裝](/help/components/c-marketing-channels/c-getting-started-mchannel.md)。

### 必備條件 {#prereqs}

如有必要，請連絡 ClientCare 以協助您釐清這些必要條件：

* 在管理控制台 (一般帳戶設定) 中，啟用報表套裝的&#x200B;**[!UICONTROL 轉換級別]** (電子商務) 選項。

   如需詳細資訊，請參閱 Analytics 說明中的[一般帳戶設定](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/admin-tools/general-acct-settings-admin.html)。

* 設定「行銷管道」維度的存取權。

   請參閱[行銷管道權限](/help/components/c-marketing-channels/c-channel-report-access.md)。

* 確認帳戶管理員已為您的報表套裝啟用&#x200B;**[!UICONTROL 管道報表]**。

### 重要處理說明 {#important-proc-rules}

* 系統以您指定的順序來處理規則，當符合規則後，即停止處理剩餘規則。
* 規則可以存取 VISTA 已設定的變數，但無法存取 VISTA 已刪除的資料。
* 管道僅儲存轉換量度。流量量度不可用。
* 兩個行銷管道絕不接收同一事件 (例如購買或點按) 的評分。這將行銷管道與 eVars (兩個 eVars 可接收同一事件的評分) 區分開來。
* 報表一次最多可處理 25 個管道。

