---
title: 階層
description: 可用於報表的自訂維度。
feature: Dimensions
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 22%

---

# 階層

>[!IMPORTANT]
>
>此維度已淘汰，且不是Analysis Workspace中的可用維度。 Adobe 建議改用 [eVar](evar.md) 和分類。

階層是自訂變數，您可以視需要使用。 這類變數在其設定所在的點擊過後即不存在。如果您的Adobe合約支援，最多可使用5個階層。

## 將資料填入階層

每個階層都會從 [`h1` - `h5` 查詢字串](/help/implement/validate/query-parameters.md) 在影像要求中。 例如， `h1` 查詢字串參數會收集階層1的資料，而 `h4` 查詢字串參數會收集階層4的資料。

AppMeasurement (會將 JavaScript 變數編譯為影像要求以進行資料收集) 會使用變數 `hier1` - `hier5`。請參閱 [hier](/help/implement/vars/page-vars/hier.md) （在「實作」使用指南中）。

## 維度項目

由於階層包含您實作中的自訂字串，因此您的組織會決定每個階層的維度項目。 請務必將每個階層的用途和一般維度項目記錄在 [解決方案設計檔案](/help/implement/prepare/solution-design.md).
