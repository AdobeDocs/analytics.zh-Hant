---
description: 與資料摘要相關的常見問題
keywords: 資料摘要, 工作, 前置欄, 後置欄, 區分大小寫
title: 資料摘要常見問答集
exl-id: 1bbf62d5-1c6e-4087-9ed9-8f760cad5420
translation-type: tm+mt
source-git-commit: c6d4095fdf86be52c7921aed84b9229ac3b27f82
workflow-type: tm+mt
source-wordcount: '420'
ht-degree: 77%

---

# 資料摘要常見問答集

與資料摘要相關的常見問題。

## 具有 `post_` 首碼的欄與沒有 `post_` 首碼的欄有何不同?

不含 `post_` 首碼的欄包含的資料與資料收集所收到的資料完全相同。具有 `post_` 首碼的欄則包含處理完成後的值。會造成值變更的原因包括變數的持續沿用、處理規則、VISTA 規則、貨幣轉換或 Adobe 套用的其他伺服器端邏輯。Adobe 建議您盡可能使用 `post_` 版本的欄。

如果欄不含 `post_` 版本 (例如 `visit_num`)，則該欄可視為後置欄。

## 資料摘要是否區分大小寫?

在 Adobe Analytics 中，為了報表呈現目的，大部分的變數都不區分大小寫。舉例來說，「snow」、「Snow」、「SNOW」和「sNow」都是相同的值。資料摘要則會區分大小寫。

如果您在非後置欄和後置欄中看到同一值的不同大小寫變化形 (例如，前置欄中是「snow」，後置欄中是「Snow」)，表示您實施作業時在網站中同時使用了同一值的大寫和小寫版本。前置欄中的大小寫變化形是在之前傳入並儲存在虛擬 cookie 中，或是與該報表套裝在大約相同的時間處理。

## 是否會將 Admin Console 機器人規則篩選的機器人加入資料摘要中？

資料摘要不會加入 [Admin Console 機器人規則](https://docs.adobe.com/content/help/zh-Hant/analytics/admin/admin-tools/bot-removal/bot-removal.html)篩選的機器人。

## 我為什麼在 `event_list` 或 `post_event_list` 資料摘要欄內看到多個 `000` 值？

有些試算表編輯器 (尤其是 Microsoft Excel) 會自動捨去非常大的數字。`event_list` 欄含有許多以逗號分隔的數字，有時候會導致 Excel 將其視為一個大數字。這會捨去末尾多個位數至 `000`。

Adobe 不建議自動開啟 Microsoft Excel 中的 `hit_data.tsv` 檔案；另外改用 Excel 的匯入資料對話框，並確定所有欄位會被視為文字。

## 為什麼我無法從超過7天的資料擷取「每小時」檔案？

對於7天以上的資料，一天的「每小時」檔案會合併為單一「每日」檔案。

範例：2021年3月9日會建立新的資料饋送，2021年1月1日至3月9日的資料會以「每小時」的形式傳送。 不過，2021年3月2日之前的「每小時」檔案會合併為單一「每日」檔案。 您只能從建立日期少於7天的資料擷取「每小時」檔案。 在本例中，從3月2日到3月9日。
