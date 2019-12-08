---
description: 您可複製 eVar 的值至 prop，以啟用路徑。
subtopic: Processing rules
title: 將 eVar 值複製至 Prop 以判斷路徑
topic: Admin tools
uuid: 8d7647c7-aa91-466b-8d31-fb4dce83f04a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 將 eVar 值複製至 Prop 以判斷路徑

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

