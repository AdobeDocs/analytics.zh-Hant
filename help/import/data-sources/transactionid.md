---
title: 交易 ID 資料來源
description: 了解使用交易 ID 資料來源的一般工作流程。
feature: Data Sources
exl-id: 5f26b15c-8d9c-46d5-860f-13fdfa21af2e
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 7%

---

# 交易 ID 資料來源

交易ID資料來源是摘要資料來源的變數，可讓您將線上和離線資料繫結在一起。 若要使用此功能，請在 Analytics 實作中使用 [`transactionID`](/help/implement/vars/page-vars/transactionid.md) 變數。

* 如果資料來源檔案中的某列含有與AppMeasurement已收集之交易ID相符的交易ID，則維度和量度會附加至線上點選。
* 如果資料來源檔案中的列包含不含相符專案的交易ID，則該列的處理方式與摘要資料來源類似。

>[!NOTE]
>
>在使用交易ID資料來源之前，您必須先在所需報表套裝的[一般帳戶設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)中啟用它。

當您傳送包含[`transactionID`](/help/implement/vars/page-vars/transactionid.md)值的線上點選時，Adobe會對當時所有已設定或持續存在的變數拍攝「快照」。 如果找到透過資料來源上傳的相符交易ID，離線和線上資料就會繫結在一起。

交易ID資料來源有下列屬性：

* 必須先收集和處理線上資料。 如果交易ID資料來源是在報表套裝處理符合該交易ID的點選之前上傳，則不會連結資料。
* 透過AppMeasurement收集的交易ID會在約90天後過期。 如果您的組織需要較長的交易ID視窗，請聯絡Adobe客戶服務。
* 以過期交易ID上傳的資料來源，其處理方式與沒有交易ID上傳的資料類似。
* 如果線上點選和交易ID資料來源中同時包含相同變數，則會使用交易ID資料來源的值。
* 如果變數包含線上上點選中，但未包含在相符的交易ID資料來源點選中，則會保留線上點選變數。
* 如果您在多個線上點選上設定相同的交易ID，則只有第一個發生次數會與來自相符交易ID資料來源的資料發生變更。
* 如果您為相同維度的多個資料來源列設定相同的交易ID，則會使用最新的維度專案。

例如：

1. 您從AppMeasurement傳送頁面檢視，其中：
   * `eVar1`等於`blue`
   * `eVar2`等於`water`
   * `events`等於`event1`
   * `transactionID`等於`1256`
2. 收集並處理點選後，您可上傳交易ID資料來源，其中：
   * `eVar1`等於`yellow`
   * `eVar3`等於`bird`
   * `events`等於`event2`
   * `transactionID`等於`1256`
3. 處理資料來源點選後，您即可在工作區中檢視報表。 資料會顯示下列內容：
   * `eVar1`等於`yellow`
   * `eVar2`等於`water`
   * `eVar3`等於`bird`
   * `events`等於`event2`

報表中不存在eVar1值`blue`和`event1`量度，因為交易ID點選會覆寫這些個別值。
