---
name: Mobile lifecycle metrics
description: 此量度是以使用 Mobile SDK 收集之資料為基礎。
feature: Metrics
source-git-commit: fa9ba599ccc3d6fe1176e6b2ec20457f30cb5959
workflow-type: ht
source-wordcount: '38'
ht-degree: 100%

---

# 行動生命週期量度

| 生命週期量度名稱 | 說明 | 上下文資料變數 |
| --- | --- | --- |
| 首次啟動 | | `a.InstallEvent` |
| 升級 | | `a.UpgradeEvent` |
| 啟動 | | `a.LaunchEvent` |
| 當機 | | `a.CrashEvent` |
| 工作階段長度總計 | | 待定 |
| 動作時間總計 | | `a.action.time.total` |
| 應用程式中的動作時間 | | `a.action.time.inapp` |
| 期限值 (事件) | | `a.ltv.amount` |

{style="table-layout:auto"}
