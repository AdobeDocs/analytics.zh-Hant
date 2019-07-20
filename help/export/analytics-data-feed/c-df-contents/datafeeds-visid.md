---
description: 'null'
keywords: 資料饋送；工作；訪客；Experience Cloud ID；分析訪客ID；identify
seo-description: 'null'
seo-title: 識別訪客
solution: Analytics
title: 識別訪客
topic: Reports & Analytics
uuid: 2490b67e-a333-422d-82fa-cb0670 ef2 e0 c
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 識別訪客

Analytics 提供數種識別訪客的機制 (列在[識別訪客](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#concept_BE966BABA7D0475BB706BC6676B8FA11)中)。Regardless of the method used to identify a visitor, in data feeds the final visitor ID used by Analytics is split across the `post_visid_high` and `post_visid_low` columns, even when using the Identity Service.

**識別獨特訪客:**

1. Exclude all rows where `exclude_hit > 0`.
1. Exclude all rows with `hit_source = 5,7,8,9`. 5、8 和 9 是使用資料來源上傳的摘要行。7 代表不應納入瀏覽次數和訪客計數的交易 ID 資料來源上傳。請參閱 [點擊來源查閱](../../../export/analytics-data-feed/c-df-contents/datafeeds-hit-source.md#concept_FE4C114F6A524F7593D5CAC944C36C42)
1. Combine `post_visid_high` with `post_visid_low`. All hits across all dates that contain this combination of `post_visid_high` and `post_visid_low` can be considered as coming from same visitor.

如果想知道是使用哪一個機制決定訪客 ID 值 (例如，計算 cookie 接受度)，`post_visid_type` 包含查閱索引鍵，可指出使用哪個 ID 方法。[下表](../../../export/analytics-data-feed/c-df-contents/datafeeds-visid.md#table_D267D36451F643D1BB68AF6FEAA6AD1A)中並列查閱索引鍵和訪客 ID 機制。

## Experience Cloud ID {#section_1628ED37D31E4B0EB75632E397A06B29}

報告的 Experience Cloud ID 另外列在 `mcvisid` 欄中。因為此 ID 以自己的一欄報告，可能無法確定 Analytics 是使用此 ID 或其他 ID 來識別訪客。

If the Experience Cloud ID was used to identify the visitor, the ID will be contained in the `post_visid_high` and `post_visid_low` columns and the `post_visid_type` will be set to 5. When calculating metrics, you should use the value from the `post_visid_high` and `post_visid_low` columns since these columns will always contain the final visitor ID.

>[!TIP]
>
> When using the Adobe Analytics visitor ID as a key for other systems, always use `post_visid_high` and `post_visid_low`. 這些欄位是唯一能保證在資料饋送的每一列都具有值的訪客 ID 欄位。

## Analytics 訪客 ID {#section_DE1DC9FC9B6D4388995B70E35B8BCDDF}

Analytics 有數種識別訪客的方式 (依偏好設定順序列在下表之中): 

| 使用順序 | 查詢參數 (收集方法) | post_visid_type 欄的值 | 發生條件 |
|---|---|---|---|
| ![](assets/step1_icon.png) | [vid (s.visitorID)](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_custom) | 0 | 已設定 s.visitorID。 |
| ![](assets/step2_icon.png) | [aid (s_vi cookie)](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_analytics) | 3 | 在您部署訪客 ID 服務之前訪客已有 s_vi cookie，或是您有設定訪客 ID 的[寬限期](https://marketing.adobe.com/resources/help/en_US/mcvid/?f=mcvid_grace_period)。 |
| ![](assets/step3_icon.png) | [mid(由Identity Service設定的AMCV_ Cookie)](https://marketing.adobe.com/resources/help/en_US/mcvid/) | 5 | 訪客的瀏覽器接受Cookie(第一方)，並部署Identity Service。 |
| ![](assets/step4_icon.png) | [fid (H.25.3 或更新版本或是 AppMeasurement for JavaScript 上的後援 cookie)](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_fallback) | 4 | 訪客的瀏覽器接受 cookie (第一方)。 |
| ![](assets/step5_icon.png) | [HTTP 行動訂閱者標題](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_mobile) | 2 | 將裝置識別為行動裝置。 |
| ![](assets/step6_icon.png) | [IP 位址、使用者代理、閘道 IP 位址](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_fallback) | 1 | 訪客的瀏覽器不接受 cookie。 |

在許多案例中，您可能會看到一個呼叫有 2 或 3 個不同 ID，但 Analytics 會使用此清單中第一個 ID 做為正式的訪客 ID，並將該值拆分到 `post_visid_high` 和 `post_visid_low` 欄。例如，如果您設定自訂訪客 ID (內含於 "vid" 查詢參數中)，則在同一個點擊可能存在其他 ID 時，將優先使用該自訂訪客 ID。
