---
description: 您可複製 eVar 的值至 prop，以啟用路徑。
seo-description: 您可複製 eVar 的值至 prop，以啟用路徑。
seo-title: 將eVar值複製至prop以判斷路徑
solution: Analytics
subtopic: 處理規則
title: 將eVar值複製至prop以判斷路徑
topic: 管理工具
uuid: 8d7647c-aa91-466b-8d31-fb4 dce83 f04 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 將eVar值複製至prop以判斷路徑

您可複製 eVar 的值至 prop，以啟用路徑。

設定值時，是由左側的變數接受右側變數的值 (即使它是空的)。

| 規則集 | 值 |
|---|---|
| 條件 | 無 (一律執行) |
| 動作 | 以 eVar1 覆寫 Prop1 的值 |

您可以修改此規則為只有在 Prop1 尚未包含值時才設定 Prop1 的值，如下所示:

| 規則集 | 值 |
|---|---|
| 條件 | 如果 Prop1 未設定 |
| 動作 | 以 eVar1 覆寫 Prop1 的值 |

例如:

![](assets/overwrite-empty-prop.png)

