---
title: 建立分類集
description: 建立分類設定時可用的欄位和說明。
exl-id: 6d692d90-8cc7-4306-a780-58d03db45be8
feature: Classifications
source-git-commit: 811e321ce96aaefaeff691ed5969981a048d2c31
workflow-type: tm+mt
source-wordcount: '188'
ht-degree: 22%

---

# 建立分類集

您可以使用分類設定管理員來建立分類設定。

**[!UICONTROL 元件]** > **[!UICONTROL 分類設定]** > **[!UICONTROL 設定]** > **[!UICONTROL 新增]**

建立分類設定時，以下欄位可供使用。

* **[!UICONTROL 名稱]**：用來識別分類集的文字欄位。 此欄位無法在建立時即進行編輯，但可稍後重新命名。
* **[!UICONTROL 欄名稱]**：您要建立的第一個分類維度名稱。 此欄位是Analysis Workspace中使用的維度名稱，以及匯出分類資料時的欄名稱。 建立分類設定後，您可以新增更多欄名稱。
* **[!UICONTROL 類型]**：指示分類類型的選項按鈕。通常會使用主要分類；查詢分類代表[子分類](../../c-sub-classifications.md)。
* **[!UICONTROL 訂閱]**&#x200B;套用此分類集的報表套裝和維度。 您可以將多個報表套裝和維度組合新增至「分類設定」。

![建立「分類設定」](../../assets/classification-set-create.png)

如果特定報告套裝+變數存在分類設定，則會將分類新增至結構描述。 指定的報告套裝+變陣列合不得屬於多個分類設定。
