---
description: 「時間分段」功能會擷取所收集的點擊的時間戳記，並採用更有意義的維度加以分段，例如「小時」或「星期」。
title: 時間分段維度
feature: Dimensions
role: User, Admin
exl-id: 92fbcc1e-1f7f-405a-8ad1-199fb7ba505e
source-git-commit: d7a6867796f97f8a14cd8a3cfad115923b329c7c
workflow-type: tm+mt
source-wordcount: '235'
ht-degree: 96%

---

# 時間分段維度

「時間分段」功能會擷取所收集的點擊的時間戳記，並採用更有意義的維度加以分段，例如「小時」或「星期」。


>[!BEGINSHADEBOX]

如需示範影片，請參閱![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Time=parting dimensions](https://video.tv.adobe.com/v/23727?quality=12&learn=on){target="_blank"}。

>[!ENDSHADEBOX]


時間分段維度是以報表套裝或虛擬報表套裝的時區為基礎。這類維度是由 Analysis Workspace 所提供，並且可以協助回答以下問題：

* 以長久的日期範圍來看，一天之中何時是訪客最常存取我的網站或應用程式的熱門時段？
* 在我的網站或應用程式中，是「星期」還是「小時」的轉換率較高？
* 週末的銷售情形與工作日的銷售情形是否有差異？
* 某個促銷活動是否在上午或下午產生較高的轉換率？

>[!NOTE]
>
>時間分段維度僅可在 Analysis Workspace 中使用。若要在其他 Analytics 解決方案中使用時間分段維度，您可以執行 [getTimeParting 外掛程式](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/gettimeparting.html?lang=zh-Hant)。

Analysis Workspace 中的時間分段維度包括：

| 維度 | 範例值 |
| --- | --- |
| 小時 | 0-23 |
| 上午/下午 | 上午、下午 |
| 星期 | 星期一、星期二、星期三、星期四、星期五、星期六、星期日 |
| 週末/平常日 | 週末、平常日 |
| 日期 | 1-31 |
| 月份 | 1月至 12 月 |
| 一年當中的第幾天 | 1-366 |
| 季別 | 第 1 季、第 2 季、第 3 季、第 4 季 |
