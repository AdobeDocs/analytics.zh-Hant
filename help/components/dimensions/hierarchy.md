---
title: 階層
description: （已淘汰）可用於報表的自訂維度。
feature: Dimensions
exl-id: f9bd3ae1-3578-44c5-a540-ea93feac5bef
source-git-commit: 75ae77c1da1b578639609888e794e13d965ef669
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 86%

---

# 階層

>[!IMPORTANT]
>
>此維度已遭到淘汰，無法使用 [維度](overview.md) 在Analysis Workspace中。 Adobe 建議改用 [eVar](evar.md) 和分類。

階層是自訂變數，您可以視需要使用。這類變數在其設定所在的點擊過後即不存在。在您的 Adobe 合約支援的前提下，最多可使用 5 個階層。

## 將資料填入階層中

每個階層會分別從影像要求中的 [`h1` - `h5` 查詢字串](/help/implement/validate/query-parameters.md)收集資料。例如，`h1` 查詢字串參數會收集階層 1 的資料，而 `h4` 查詢字串參數則會收集階層 4 的資料。

AppMeasurement (會將 JavaScript 變數編譯為影像要求以進行資料收集) 會使用變數 `hier1` - `hier5`。如需實作準則，請參閱「實作」使用手冊中的 [階層](/help/implement/vars/page-vars/hier.md)。

## 維度項目

由於階層包含您實作中的自訂字串，因此您的組織會決定每個階層的維度項目。請務必將每個階層的用途和常用的維度項目記錄在[解決方案設計文件](/help/implement/prepare/solution-design.md)中。
