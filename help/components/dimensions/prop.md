---
title: Prop
description: 可用於報告的自訂維度。
feature: Dimensions
exl-id: cf8ad65b-bc54-473e-bcfc-9c981d23e782
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '471'
ht-degree: 93%

---

# Prop

*此說明頁面說明Prop作為[維度](overview.md)時的運作方式。 如需如何實作 Prop 的相關資訊，請參閱「實作」使用指南中的 [Prop](/help/implement/vars/page-vars/prop.md)。*

Prop 是自訂變數，您可以視需要使用。這類變數在其設定所在的點擊過後即不存在。

>[!TIP]
>
>Adobe 建議在大部分情況下使用 [eVar](evar.md)。在舊版 Adobe Analytics 中，prop 和 eVar 各有其優缺點。不過 Adobe 已改良 eVar，現在它們幾乎能完成 prop 的所有使用案例。

如果您有[解決方案設計文件](/help/implement/prepare/solution-design.md)，您可以將這些自訂維度配置給組織的特定值。可用的 Prop 數量取決於您與 Adobe 訂定的合約。在您的 Adobe 合約支援的前提下，最多可使用 75 個 Prop。

## 將資料填入 Prop 中

每個 Prop 會分別從影像要求中的 [`c1` - `c75` 查詢字串](/help/implement/validate/query-parameters.md)收集資料。例如，`c1` 查詢字串參數會收集 prop1 的資料，而 `c68` 查詢字串參數則會收集 prop68 的資料。

AppMeasurement (會將 JavaScript 變數編譯為影像要求以進行資料收集) 會使用變數 `prop1` - `prop75`。如需實作準則，請參閱「實作」使用指南中的 [Prop](/help/implement/vars/page-vars/prop.md)。

## 維度項目

由於 Prop 包含您實作中的自訂字串，因此您的組織會決定每個 Prop 的維度項目。請務必將每個Prop的用途和常用的維度專案記錄在[解決方案設計檔案](/help/implement/prepare/solution-design.md)中。

## 區分大小寫

Prop 預設不區分大小寫。如果您以不同大小寫傳送相同的值 (例如 `"DOG"` 和 `"Dog"`)，Analysis Workspace 會將它們分組到相同的維度項目中。系統會使用報告月份開頭所見第一個值的大小寫。Data Warehouse 會顯示在請求期間遇到的第一個值。

您可以將任何 prop 設為區分為大小寫。您也可以在任何 prop 啟用後，停用其區分大小寫的功能。聯絡 Adobe客戶服務並提供報表套裝 ID 和所需的變數，以切換區分大小寫功能。

>[!WARNING]
>
>切換區分大小寫功能可能會截斷維度項目、造成區段產生非預期結果，以及導致篩選器問題。Adobe 強烈建議在兩個主要時段之間切換此設定，例如月初或年初。

## Prop 優於 eVar 之處

Adobe 建議在大部分情況下使用 eVar。其例外情況如下：

* 您可以在即時報表中使用 Prop。eVar 至少需要 30 分鐘才能顯示在報表中。
* prop 可成為清單屬性，這些 prop 能在同一次點擊中接受多個值。清單變數是個別的變數，而且只有三個清單變數可供使用。
* 當您對 Prop 啟用路徑分析時，[登入](entry-dimensions.md)和[退出](exit-dimensions.md)維度會立即變成可用狀態。如果您想要使用 eVar 的登入和退出維度，可以手動建立區段。

如需 Prop 與 eVar 之間的更多比較，請參閱 [eVar](evar.md)。
