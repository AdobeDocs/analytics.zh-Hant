---
title: hier
description: （已淘汰）在Adobe Analytics中實作階層變數。
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
role: Admin, Developer
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 93%

---

# hier

>[!IMPORTANT]
>
>此變數已遭到淘汰，在 Analysis Workspace 中不是可用維度。Adobe 建議改用 [eVar](evar.md) 和分類。

階層變數是可讓您查看網站結構的自訂變數。Adobe 在實作中支援最多 5 個階層變數。

此變數對於擁有超過三層結構的網站很實用。例如，媒體網站的「運動」區段可以有 4 個層級：`Sports`、`Local Sports`、`Baseball` 和 `Team name`。若有人瀏覽了「棒球」頁面，則「運動」、「地方運動」和「棒球」等層級全都會反映該次瀏覽。

在實作中使用階層之前，請務必先在報表套裝設定中設定每個階層。

## 使用 Web SDK 的階層

階層會[為 Adobe Analytics 進行對應](/help/implement/aep-edge/xdm-var-mapping.md)，在 XDM 欄位 `xdm._experience.analytics.customDimensions.hierarchies.hier1` 至 `xdm._experience.analytics.customDimensions.hierarchies.hier5` 底下。

## 使用 Adobe Analytics 擴充功能的階層

您可以在設定 Analytics 擴充功能 (全域變數) 時或是在規則底下設定階層。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下所需的標籤屬性。
3. 前往[!UICONTROL 規則]標籤，然後按一下所需的規則 (或建立規則)。
4. 在[!UICONTROL 「動作」]下方按一下現有的[!UICONTROL 「Adobe Analytics - 設定變數」]動作，或按一下「+」圖示。
5. 設定 [!UICONTROL 副檔名] Adobe Analytics的下拉式清單，以及 [!UICONTROL 動作型別] 至 [!UICONTROL 設定變數].
6. 找出[!UICONTROL 「階層」]區段。

您可以將階層值設定為靜態字串或參考資料元素。您也可以設定所需的分隔符號。確保您在此處設定的分隔符號與報表套裝設定中所設的分隔符號相符。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.hier1 - s.hier5

每個階層都是字串，其中包含貴組織專屬的自訂值。它們的最大長度為 255 個位元組；超過 255 個位元組的值會在傳送至 Adobe 時自動截斷。

請確定您的區段名稱皆未包含分隔字元。舉例來說，如果您其中一個區段名為 `Coach Griffin, Jim`，請選擇逗號以外的分隔字元。變數總上限為 255 個位元組。分隔字元可由多個字元組成，如 `||` 或 `/|\`，這些字元不太可能出現在變數值中。

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
