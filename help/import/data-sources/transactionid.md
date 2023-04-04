---
title: 交易 ID 資料來源
description: 了解使用交易 ID 資料來源的一般工作流程。
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
source-git-commit: 54c88a275b48f2b401be450ce35767ab3ea9d40b
workflow-type: tm+mt
source-wordcount: '426'
ht-degree: 10%

---

# 交易 ID 資料來源

交易ID資料來源是摘要資料來源的變數，可讓您將線上和離線資料系結在一起。 若要使用此功能，請在 Analytics 實作中使用 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 變數。

* 如果資料來源檔案中的一列包含的交易ID符合AppMeasurement已收集的交易ID，則維度和量度會附加至線上點擊。
* 如果資料來源檔案中的列包含不含相符項目的交易ID，則該列的處理方式與摘要資料來源類似。

>[!NOTE]
>
>使用交易ID資料來源前，您必須先在 [一般帳戶設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md) 的報表套裝。

當您傳送包含 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 值時，Adobe會對所有變數集合或持續存在拍攝「快照」。 如果找到透過資料來源上傳的相符交易ID，離線和線上資料就會系結在一起。

交易ID資料來源具有下列屬性：

* 必須先收集和處理線上資料。 如果在報表套裝處理符合該交易ID的點擊前上傳交易ID資料來源，則不會連結該資料。
* 透過AppMeasurement收集的交易ID約在90天後過期。 如果您的組織需要較長的交易ID視窗，請聯絡Adobe客戶服務。
* 以過期交易ID上傳的資料來源，其處理方式與不使用交易ID上傳的資料類似。
* 如果線上點擊和交易ID資料來源中都包含相同變數，則會使用來自交易ID資料來源的值。
* 如果線上點擊中包含變數，但相符的交易ID資料來源點擊中未包含變數，則會保留線上點擊變數。
* 如果您在多個線上點擊上設定相同的交易ID，則只有第一次發生次數會隨著來自相符交易ID資料來源的資料而變更。
* 如果您針對相同的維度在多個資料來源列上設定相同的交易ID，則會使用最新的維度項目。

例如：

1. 您從AppMeasurement傳入頁面檢視，其中：
   * `eVar1` 等於 `blue`
   * `eVar2` 等於 `water`
   * `events` 等於 `event1`
   * `transactionID` 等於 `1256`
2. 收集並處理點擊後，您上傳交易ID資料來源，其中：
   * `eVar1` 等於 `yellow`
   * `eVar3` 等於 `bird`
   * `events` 等於 `event2`
   * `transactionID` 等於 `1256`
3. 處理資料來源點擊後，您即可在工作區中檢視報表。 資料會顯示下列內容：
   * `eVar1` 等於 `yellow`
   * `eVar2` 等於 `water`
   * `eVar3` 等於 `bird`
   * `events` 等於 `event2`

eVar1值 `blue` 和 `event1` 量度不存在於報表中，因為交易ID點擊會覆寫這些個別值。
