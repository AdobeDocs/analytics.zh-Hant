---
description: 您可以比對值是否有常見的拼寫錯誤，並加以更新以便在報告中正確顯示。
subtopic: Processing rules
title: 清除報表中的值
feature: 管理工具
uuid: fcd72afc-3a3c-47a9-a5e4-53389dba7d83
exl-id: 109005a3-2ea4-4b61-a733-d1019218ec56
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '115'
ht-degree: 100%

---

# 清除報表中的值

您可以比對值是否有常見的拼寫錯誤，並加以更新以便在報告中正確顯示。

為了確保不會不慎比對到其他值，請使用限制最嚴格的可用符合選項。您可對變數 (以下範例使用 prop1) 執行報告，然後搜尋您選取來進行取代的字詞，以確定不會符合非預期的值。字串比較不分大小寫。

| 規則集 | 值 |
|---|---|
| 條件 | 如果 prop1 開頭為 Shopping |
| 動作 | 將 prop1 的值覆寫為自訂值 Shopping |

例如：

![](assets/clean-up-values-in-report.png)
