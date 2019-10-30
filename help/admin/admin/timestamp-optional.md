---
description: 在單一報表套裝中，結合時間戳記與非時間戳記資料。
seo-description: 在單一報表套裝中，結合時間戳記與非時間戳記資料。
seo-title: 可選時間戳記
solution: Analytics
title: 可選時間戳記
topic: 管理工具
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 可選時間戳記

在單一報表套裝中，結合時間戳記與非時間戳記資料。

「可選時間戳記」可讓您:

* 在相同的全域報表套裝中，混搭時間戳記與非時間戳記資料。
* 從行動應用程式傳送時間戳記資料至全域報表套裝。
* 升級應用程式，即可在無需建立新報表套裝的狀況下使用離線追蹤。

如需在報表套裝中使用時間戳記的最佳實務，請參閱[使用可選時間戳記](/help/implement/js-implementation/timestamps-overview.md)。

>[!IMPORTANT]
>
>If you are using Timestamps Optional, then do not set [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_custom.html) on data that is already timestamped. 這會導致資料順序錯亂，並影響時間計算 (例如逗留時間值)、歸因 (eVar 持續性)、造訪次數/造訪計數，以及路徑報表。

> [!NOTE]啟動時間戳記的作業資料最多可保留 92 日。這表示瀏覽／工作階段將「持續開啟」92天，而任何額外點擊(在上次點擊後30分鐘（在點擊時間）內)仍可包含在同一次瀏覽／工作階段中。 任何未依序收到的「舊」點擊都會產生「未知」的結果，因為有許多因素（分段、分配、過期等）影響這些點擊是否會包含在報表中。

## 新的報表套裝 {#section_095A7CFBD280494593B9BEC1592B73A6}

* 如果是從範本建立，新的報表套裝預設為使用「可選時間戳記」。

   (若要從範本建立新的報表套裝，請至&#x200B;**「管理員 &gt; 報表套裝 &gt; 新建 &gt; 報表套裝」**。)
* 若是從現有的報表套裝複製，則新的報表套裝會繼承原始報表套裝的時間戳記設定，包括:

   * **不允許時間戳記** (支援設定 s.visitorID)
   * **必要時間戳記** (不支援設定 s.visitorID)
   * **可選時間戳記** (支援設定 s.visitorID，但不適用於時間戳記的點擊上)

## 若要將現有的報表套裝變更為可選時間戳記 {#section_40BCD3B4639241DEA716F7640ED33E72}

1. 前往&#x200B;**「管理員 &gt; 報表套裝 &gt; 編輯設定 &gt; 一般 &gt; 時間戳記設定」**。
1. 選取&#x200B;**「將所選的報表套裝轉換為可選時間戳記」**&#x200B;方塊。

   這會將您的報表套裝變更為「可選時間戳記」。

> [!NOTE] 如果報表套裝設為「可選 **時間戳記」**，若要將此變更為任何其他設定，請連絡Adobe客戶服務。

