---
title: list
description: 在同一次點擊中容納多個值的自訂變數。
feature: Appmeasurement Implementation
exl-id: 612f6f10-6b68-402d-abb8-beb6f44ca6ff
role: Admin, Developer
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 74%

---

# list

清單變數是自訂變數，您可以視需要使用。它們的作用與 eVar 類似，但是它們可以在同一次點擊中包含多個值。清單變數沒有字元限制。

請務必將每個清單變數的使用方式與其邏輯記錄在[解決方案設計文件](../../prepare/solution-design.md)內。

>[!NOTE]
>
>清單變數會根據[!UICONTROL 報表套裝設定]中的[最大值](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)設定，儲存每位訪客最近的值。 最多可支援250個值。 如果唯一值的數量超過[!UICONTROL 最大值]設定所允許的數量，則最早的值不會歸屬於量度。

## 在報表套裝設定中設定清單變數

在實施中使用清單變數之前，請務必先在報表套裝設定中設定每個變數。請參閱「管理員指南」中的[轉換變數](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)。此步驟適用於所有實作方法。

## 使用 Web SDK 的清單變數

如果使用&#x200B;[**XDM物件**](/help/implement/aep-edge/xdm-var-mapping.md)，清單變數會使用XDM欄位`xdm._experience.analytics.customDimensions.lists.list1.list[]`至`xdm._experience.analytics.customDimensions.lists.list3.list[]`。 每個陣列元素包含一個 `"value"` 物件，其中包含每個字串。不需要提供分隔符號；Adobe資料收集伺服器會自動偵測並包含[報表套裝設定](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)中設定的正確分隔符號。

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

如果使用&#x200B;[**資料物件**](/help/implement/aep-edge/data-var-mapping.md)，清單變數會依照AppMeasurement語法使用`data.__adobe.analytics.list1` - `data.adobe.analytics.list3`。 請確定您在[報表套裝設定](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)中使用正確的分隔符號集。

```json
"data": {
  "__adobe": {
    "analytics": {
      "list1": "Example value 1,Example value 2,Example value 3"
    }
  }
}
```

## 使用 Adobe Analytics 擴充功能的清單變數

Adobe Analytics 擴充功能中沒有專用欄位可使用這個變數。請依照 AppMeasurement 語法使用自訂程式碼編輯器。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.list1 - s.list3

每個清單變數都是字串，其中包含貴組織專屬的自訂值。此變數沒有位元組數上限，不過每個個別值都有最多255個位元組的限制。 您使用的分隔字元，可以在 [報表套裝設定](/help/admin/tools/manage-rs/edit-settings/conversion-var-admin/list-var-admin.md)中設定變數時決定。在分隔多個項目時，請勿使用空格。

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
