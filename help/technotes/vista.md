---
title: Adobe Analytics 中的 VISTA 規則
description: 進一步了解 VISTA 規則及其功能。
exl-id: fab2acc3-b037-48f9-bb20-625ccb75b4cc
feature: Analytics Basics
source-git-commit: b1c22031b9254ff077dfdc04ab90ab231b504299
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 57%

---

# Adobe Analytics 中的 VISTA 規則

VISTA 規則是自訂資料修改的另一種形式，您可以在資料收集和處理之間應用。請參閱[處理順序](processing-order.md) 以進一步了解 VISTA 規則套用之資料管道中的確切階段。VISTA 規則僅影響收集的目前資料；它不會改變現有資料。

VISTA 規則的一些常見使用案例包括：

* 將 Analytics 點擊從一個報告套裝複製到另一個報告套裝，可選擇更改所複製報告套裝的資料
* 自訂 IP 排除超過[依 IP 排除](/help/admin/tools/exclude-ip.md)提供的使用案例
* 有條件地或全域地修改任何變數值
* 將變數值複製到其他變數
* 將可能影響變數值的檔案上傳到 Adobe FTP 站台

[處理規則](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-overview.md)、[機器人規則](/help/admin/tools/manage-rs/edit-settings/general/bot-removal/bot-rules.md)、[虛擬報告套裝](/help/components/vrs/vrs-about.md)已經提供了 VISTA 規則的許多使用案例，或者只是更新您的 Adobe Analytics 實施。Adobe 建議僅將 VISTA 規則作為最後的手段。

>[!IMPORTANT]
>
>VISTA規則實施和設定需要貴組織與Adobe Professional Services之間達成付費協定。 如果您想要建立或更新VISTA規則，請聯絡您的Adobe客戶團隊。
>
>請注意：
>
>* VISTA規則建立僅包含初始實施。 持續維護或VISTA規則更新需要單獨的付費參與。
>
>* VISTA規則取決於您資料中的特定條件。 例如，變更您的Adobe Analytics實作、收集的資料型別或字串長度、變更用於DB VISTA的表格，或對輸入資料模式進行其他變更，可能會導致VISTA規則停止如預期運作。 Adobe建議定期檢閱您的VISTA規則，以決定是否需要更新或移除。

## 建立 VISTA 規則 {#create}

您必須使用 Adobe Professional Services 才能建立 VISTA 規則。如果您想要建立VISTA規則，請聯絡您的Adobe客戶團隊。

## 請參閱現有的 VISTA 規則 {#see}

Adobe 不提供可檢視現有 VISTA 規則的 UI。聯絡您的Adobe客戶團隊或客戶服務，提供所需的報表套裝，以擷取現有VISTA規則清單。
