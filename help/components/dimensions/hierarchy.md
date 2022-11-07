---
title: 階層
description: 可用於報表的自訂維度。
feature: Dimensions
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: ht
source-wordcount: '163'
ht-degree: 100%

---

# 階層

>[!IMPORTANT]
>
>此維度已遭到淘汰，在 Analysis Workspace 中不是可用維度。Adobe 建議改用 [eVar](evar.md) 和分類。

階層是自訂變數，您可以視需要使用。這類變數在其設定所在的點擊過後即不存在。在您的 Adobe 合約支援的前提下，最多可使用 5 個階層。

## 將資料填入階層中

每個階層會分別從影像要求中的 [`h1` - `h5` 查詢字串](/help/implement/validate/query-parameters.md)收集資料。例如，`h1` 查詢字串參數會收集階層 1 的資料，而 `h4` 查詢字串參數則會收集階層 4 的資料。

AppMeasurement (會將 JavaScript 變數編譯為影像要求以進行資料收集) 會使用變數 `hier1` - `hier5`。如需實作準則，請參閱「實作」使用手冊中的 [階層](/help/implement/vars/page-vars/hier.md)。

## 維度項目

由於階層包含您實作中的自訂字串，因此您的組織會決定每個階層的維度項目。請務必將每個階層的用途和常用的維度項目記錄在[解決方案設計文件](/help/implement/prepare/solution-design.md)中。
