---
title: 使用Adobe Analytics標籤擴充功能的訪客身分識別
description: 實作Adobe Analytics標籤擴充功能時正確識別訪客。
source-git-commit: 5bd1914dc52c664348f30793761f0fc347343156
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# 使用Adobe Analytics標籤擴充功能的訪客身分識別

Adobe Analytics標籤擴充功能可讓您使用標籤管理介面實施AppMeasurement。 由於此標籤擴充功能本質上是隱藏的AppMeasurement，因此提供類似的方法來識別訪客，並要求為訪客ID服務使用個別的標籤擴充功能。

## 使用訪客ID服務識別訪客（建議）

若要使用Adobe Analytics標籤擴充功能來使用訪客ID服務，請在標籤屬性中加入Experience Cloud ID服務標籤擴充功能。

1. 使用您的Adobe ID憑證登入[experience.adobe.com](https://experience.adobe.com)。
1. 導覽至&#x200B;**[!UICONTROL 資料彙集]** > **[!UICONTROL 標籤]**。
1. 找到所需的標籤屬性。
1. 導覽至&#x200B;**[!UICONTROL 擴充功能]**，然後選取&#x200B;**[!UICONTROL 目錄]**&#x200B;索引標籤。
1. 找到&#x200B;**[!UICONTROL Experience Cloud ID服務]**&#x200B;擴充功能，然後選取&#x200B;**[!UICONTROL 安裝]**。

標籤擴充功能會自動取得您的IMS組織ID，因此不需要額外設定。

## 使用`s_vi` Cookie識別訪客（不建議）

>[!IMPORTANT]
>
>Adobe建議不要使用此方法來識別訪客。

如果您的組織未使用訪客ID服務標籤擴充功能，Adobe Analytics標籤擴充功能將使用其本身的訪客身分識別形式。 當訪客首次進入您的網站時，擴充功能會檢查[`s_vi`](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/data-collection/cookies/analytics) Cookie。 當&#x200B;**[!UICONTROL 設定標籤延伸模組]**&#x200B;時，此Cookie設定在符合&#x200B;**[!UICONTROL SSL追蹤伺服器]** （適用於HTTPS）或[追蹤伺服器](https://experienceleague.adobe.com/zh-hant/docs/experience-platform/tags/extensions/client/analytics/overview) （適用於HTTP）的網域上。

* 如果您參與[Managed憑證方案](https://experienceleague.adobe.com/zh-hant/docs/core-services/interface/data-collection/adobe-managed-cert)，您的追蹤伺服器通常會是第一方網域，使`s_vi` Cookie成為第一方。
* 如果您不參與Managed憑證計畫，追蹤伺服器通常是`adobedc.net`、`omtrdc.net`或`2o7.net`的子網域，使`s_vi` Cookie成為協力廠商Cookie。 由於現今瀏覽器隱私權實務趨於嚴謹，大部分的瀏覽器都會拒絕協力廠商Cookie。 在遭到拒絕後，AppMeasurement會嘗試改為設定第一方備援Cookie (`fid`)。

如果您正確設定[!UICONTROL SSL追蹤伺服器]，則不需要進一步的訪客識別測量。

## 使用`visitorID`識別訪客（不建議）

>[!IMPORTANT]
>
>Adobe建議不要使用此方法來識別訪客。

使用&#x200B;**[!UICONTROL 訪客識別碼]**&#x200B;變數，可讓您的組織完全獨立地控制識別訪客。 如果您使用資料元素設定[!UICONTROL 訪客識別碼]，請注意下列限制：

* 每個點選都必須包含相同的[!UICONTROL 訪客識別碼]值，才能計為單一訪客。
   * 省略[!UICONTROL 訪客ID]資料元素的任何點選都會自動嘗試使用其他訪客識別方法，將其視為個別訪客。
   * 任何包含來自先前點選之不同[!UICONTROL 訪客ID]值的點選都會視為個別訪客。
   * Adobe不提供任何方式將使用不同訪客ID的點選拼接在一起。
* 使用[!UICONTROL 訪客ID]識別的訪客不支援共用受眾、Analytics for Target和Customer屬性。

如需使用此變數的實作指示，請參閱[`visitorID`](/help/implement/vars/config-vars/visitorid.md)。
