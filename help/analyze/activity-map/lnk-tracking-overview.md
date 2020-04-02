---
description: 'Activity Map 使用更強大的演算法來追蹤連結，具有下列優點 '
title: 強大的連結追蹤
topic: Activity map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 強大的連結追蹤

Activity Map 使用更強大的演算法來追蹤連結，具有下列優點：

* 包含頁面地區的追蹤，可避免由於連結顯示在頁面的不同位置，而導致不同裝置間的相同連結混淆。
* 確保連結獨特性，這表示不會因為 LinkID 問題或在不同瀏覽器間弄錯不同的連結。

如需 Activity Map 中連結追蹤的詳細資訊，請前往[此處](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md)。

## Activity Map 連結追蹤如何收集 PII 資料 {#section_AEE57510D17B4C21A7D49D32D21D67B9}

> [!CAUTION]開啟 Activity Map 追蹤功能後，您就可能會收集個人識別資訊 (PII) 資料。此資料可以單獨使用，或搭配其他資訊使用，藉以識別、聯絡或尋找個別人員，或者識別環境中的個人。

以下是可能使用 Activity Map 追蹤來收集 PII 資料的一些已知案例：

* `Mailto` 連結。Mailto 連結是一種 HTML 連結，它會啟用電腦上的預設郵件用戶端來傳送電子郵件。
* 當使用者登入後，`User ID` 連結可能會顯示在網站的標題/註腳中。
* 若為金融機構，帳號可能會以連結的型態顯示。按一下連結，就可以收集該連結的文字。
* 醫療照護網站也可能讓 PII 資料以連結的型態顯示。按一下這些連結，就可以收集該連結的文字，從而收集 PII 資料。
