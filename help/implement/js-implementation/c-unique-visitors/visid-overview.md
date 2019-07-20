---
description: Adobe 可使用 Cookie 來追蹤獨特的瀏覽器/裝置。
keywords: Analytics 實施
seo-description: Adobe 可使用 Cookie 來追蹤獨特的瀏覽器/裝置。
seo-title: 識別獨特訪客
solution: Analytics
subtopic: 訪客
title: 識別獨特訪客
topic: 開發人員和實施
uuid: ed4dee75-ecfb-4715-8122-461983c7 dd8 f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 識別獨特訪客

Adobe 可使用 Cookie 來追蹤獨特的瀏覽器/裝置。

## Analytics 訪客 ID 順序 {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Adobe Analytics 提供數個識別訪客的機制。下表列出 Analytics 中用於辨識訪客的不同方法 (依優先順序):

| 使用順序 | 查詢參數 (收集方法) | 存在時機 |
|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](../../../implement/js-implementation/c-unique-visitors/visid-custom.md#concept_4A2000F4B6ED41E99CA6118A6D74ECE8) | 設定 s.visitorID |
| ![](assets/step2_icon.png) | [aid (s_vi Cookie)](../../../implement/js-implementation/c-unique-visitors/visid-analytics.md#concept_74F6B4B9B2FA415AB5D029A1F8F099BC) | 在您部署訪客 ID 服務之前訪客已有 s_vi Cookie，或是您有設定訪客 ID 的寬限期。 |
| ![](assets/step3_icon.png) | [mid (Experience Cloud 訪客 ID 服務所設定的 AMCV_ Cookie)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 訪客的瀏覽器接受 Cookie (第一方) |
| ![](assets/step4_icon.png) | [fid (H.25.3 或更新版本的後援 Cookie，或 JavaScript 適用的 AppMeasurement)](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#concept_EBCBF9EB390E45A2BA20DB6BE931C505) | 訪客的瀏覽器接受 Cookie (第一方) |
| ![](assets/step5_icon.png) | [IP 位址、使用者代理、閘道 IP 位址](../../../implement/js-implementation/c-unique-visitors/visid-fallback.md#section_104819D74C594ECE879144FCC5DEF4BF) | 訪客的瀏覽器不接受 Cookie |

許多情況下您可能會在呼叫上看到 2 或 3 個不同的 ID，但 Analytics 會使用上表中第一個存在的 ID 做為官方訪客 ID。例如，如果您設定自訂訪客 ID (內含於 "vid" 查詢參數中)，則在同一個點擊可能存在其他 ID 時，將優先使用該自訂訪客 ID。

>[!NOTE]
>
>每個Analytics訪客ID都與Adobe伺服器上的訪客描述檔相關聯。無論訪客 ID Cookie 過期與否，訪客閒置最少 13 個月就會刪除其訪客資料。
