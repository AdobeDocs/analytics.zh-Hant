---
title: list
description: 在同一次點擊中容納多個值的自訂變數。
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
source-git-commit: 84a4d38a65769f028bac4aa5817cb4002c4b1f97
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 100%

---

# 清單

清單變數是自訂變數，您可以視需要使用。它們的作用與 eVar 類似，但是它們可以在同一次點擊中包含多個值。清單變數沒有字元限制。

請務必將每個清單變數的使用方式與其邏輯記錄在[解決方案設計文件](../../prepare/solution-design.md)內。

>[!NOTE]
>
>清單變數能儲存每位訪客最近 250 個值。如果特定訪客擁有超過 250 個獨特值，則最舊的值不會歸入量度。

## 在報表套裝設定中設定清單變數

在實施中使用清單變數之前，請務必先在報表套裝設定中設定每個變數。請參閱「管理員指南」中的[轉換變數](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)。此步驟適用於所有實作方法。

## 使用 Web SDK 的清單變數

清單變數會[為 Adobe Analytics 進行對應](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html)，在 XDM 欄位 `_experience.analytics.customDimensions.lists.list1.list[]` 至 `_experience.analytics.customDimensions.lists.list3.list[]` 底下。每個陣列元素包含一個 `"value"` 物件，其中包含每個字串。不需提供分隔符號，系統會自動使用[報表套裝設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)中指定的值加入。例如，如果逗號 (&#39;`,`) 設定為清單變數 1 的分隔符號，接下來的 XDM 物件會將 `"Example value 1,Example value 2,Example value 3"` 填入 `list1` 變數。

```json
"xdm": {
    "_experience": {
        "analytics": {
            "customDimensions": {
                "lists": {
                    "list1": {
                        "list": [
                            {
                                "value": "Example value 1"
                            },
                            {
                                "value": "Example value 2"
                            },
                            {
                                "value": "Example value 3"
                            }
                        ]
                    }
                }
            }
        }
    }
}
```

>[!NOTE]
>
>Adobe XDM 結構描述在每個 `list[]` 陣列中，除了 `value` 物件，也包含 `key` 物件。Adobe 在傳送資料給 Adobe Analytics 時，不會使用這些 `key` 物件。

## 使用 Adobe Analytics 擴充功能的清單變數

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.list1 - s.list3

每個清單變數都是字串，其中包含貴組織專屬的自訂值。它們沒有位元組數上限，不過每個個別的值有最多 255 個位元組的上限。您使用的分隔字元，可以在 [報表套裝設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/list-var-admin.md)中設定變數時決定。在分隔多個項目時，請勿使用空格。

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>如果您在同一次點擊中設定重複值，Adobe 會去除這些值的所有例項。例如，若您設定 `s.list1 = "Brick,Brick";`，報表只會計入一個例項。

## 比較清單屬性和清單變數

清單屬性和清單變數都可以在同一次點擊中包含多個值。不過，這兩種變數類型之間有幾項主要差異。

* 任何屬性都可以變成清單屬性。如果每個屬性都是清單屬性，實際上您最多可以擁有 75 個清單屬性。可用的清單變數只有 3 個。
* 清單屬性的整個變數有 100 個位元組的限制。清單變數的每個值有 255 個位元組的限制，但是沒有位元組總數限制。
* 清單屬性不會持續存在超過其設定的點擊。清單變數的過期設定可以是您想要的任何設定。不過，透過[報表時間處理](/help/components/vrs/vrs-report-time-processing.md)，您可以將自訂歸因同時套用至清單屬性和清單變數。
