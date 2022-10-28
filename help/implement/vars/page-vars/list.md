---
title: list
description: 在同一次點擊中容納多個值的自訂變數。
feature: Variables
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
source-git-commit: 25eccb2b9fe3827e62b0ae98d9bebf7a97b239f5
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 63%

---

# 清單

清單變數是自訂變數，您可以視需要使用。它們的作用與 eVar 類似，但是它們可以在同一次點擊中包含多個值。清單變數沒有字元限制。

請務必將每個清單變數的使用方式及其邏輯記錄在 [解決方案設計檔案](../../prepare/solution-design.md).

>[!NOTE]
>
>清單變數能儲存每位訪客最近 250 個值。如果特定訪客擁有超過 250 個獨特值，則最舊的值不會歸入量度。

## 在報表套裝設定中設定清單變數

在實施中使用清單變數之前，請務必先在報表套裝設定中設定每個變數。請參閱「管理員指南」中的[轉換變數](/help/admin/admin/conversion-var-admin/list-var-admin.md)。此步驟適用於所有實施方法。

## 使用Web SDK的清單變數

清單變數包括 [已對應至Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html) 在XDM欄位下 `_experience.analytics.customDimensions.lists.list1.list[]` to `_experience.analytics.customDimensions.lists.list3.list[]`. 每個陣列元素都包含 `"value"` 包含每個字串的物件。 無需提供分隔字元；會使用 [報表套裝設定](/help/admin/admin/conversion-var-admin/list-var-admin.md). 例如，若逗號(「`,`&#39;)設為清單變數1的分隔字元，下列XDM物件會填入 `list1` 變數 `"Example value 1,Example value 2,Example value 3"`.

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
>AdobeXDM架構包含 `key` 對象 `value` 每個 `list[]` 陣列。 Adobe不使用這些 `key` 物件。

## 使用Adobe Analytics擴充功能列出變數

Adobe Analytics擴充功能中沒有專用欄位可使用此變數。 請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.list1 - s.list3

每個清單變數都是字串，其中包含貴組織專屬的自訂值。它們沒有位元組數上限，不過每個個別的值有最多 255 個位元組的上限。您使用的分隔字元，是在 [報表套裝設定](/help/admin/admin/conversion-var-admin/list-var-admin.md). 在分隔多個項目時，請勿使用空格。

```js
// A list variable configured with a comma as a delimiter
s.list1 = "Example value 1,Example value 2,Example value 3";
```

>[!TIP]
>
>如果您在同一次點擊中設定重複值，Adobe 會去除這些值的所有例項。例如，若您設定 `s.list1 = "Brick,Brick";`，報表只會計入一個例項。

## 比較清單屬性和清單變數

清單屬性和清單變數都可以在同一次點擊中包含多個值。不過，這兩種變數類型之間有幾項主要差異。

* 任何屬性都可以變成清單屬性。如果每個屬性都是清單屬性，實際上您最多可以擁有 75 個清單屬性。只有三個清單變數可用。
* 清單屬性的整個變數有 100 個位元組的限制。清單變數的每個值有 255 個位元組的限制，但是沒有位元組總數限制。
* 清單屬性不會持續存在超過其設定的點擊。清單變數的過期設定可以是您想要的任何設定。不過，透過[報表時間處理](/help/components/vrs/vrs-report-time-processing.md)，您可以將自訂歸因同時套用至清單屬性和清單變數。
