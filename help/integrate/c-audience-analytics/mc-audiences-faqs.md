---
description: 回答實施作業 Audience Analytics 時可能遇到的問題。
solution: Experience Cloud
title: Audience Analytics 的常見問題集
feature: Audience Analytics
exl-id: 86e7967c-030c-44d6-8294-e7e6d41f6fc3
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 31%

---

# 常見問答

回答實施作業 Audience Analytics 時可能遇到的問題。

## 法律常見問答 {#legal}

+++ 如何知道我的Analytics資料中是否有個人識別資訊(PII)？ 如果有，我該怎麼做？

如果您的prop或eVar中有電子郵件/地址/等，請考慮在收集期間對資料進行雜湊處理。 如果您的國家/地區認為IP位址是PII，請[開啟IP模糊化](/help/admin/tools/exclude-ip.md)。 請洽詢Analytics管理員，瞭解您正在收集哪些資料。 請洽詢您的法律部門，瞭解他們對PII的看法。

+++

+++ 如何知道我的報表套裝是進行站上個人化，還是離站/站上鎖定？

這不適用於將Adobe Analytics資料傳送至Adobe Audience Manager。 問問自己：

* 您是否會將Analytics共用區段與Experience Cloud中的MCA維度共用？

* 您是否匯出 (例如透過資料饋送) 至用於這些目的的商業智慧 (BI) 系統？

+++

## Adobe Audience Manager專屬常見問答 {#aam-specific}

+++ 如何在Audience Manager中建立Analytics目的地？

請參閱「[在Adobe Audience Manager中設定Analytics目的地](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/experience-cloud-destinations/create-analytics-destination.html?lang=zh-Hant)」。

+++

+++ 建立和儲存Analytics目的地後，需要多久才會在我選取的報表套裝中顯示資料？

將新資料填入您的報表套裝可能需要數小時。

+++

+++ 我已建立新的Analytics目的地，但在可用區段的「目的地對應」區段中看不到。 這個目的地在哪裡，我要如何找到？

當您在「**[!UICONTROL 區段對應]**」中選取「**[!UICONTROL 自動對應所有目前和未來的區段]**」選項時，Analytics目的地會從區段的「目的地對應」區段消失。 要防止此情況，請選取&#x200B;**[!UICONTROL 「手動對應區段」]**&#x200B;來取代自動選項。

+++

此功能可否在Analytics提供來自Adobe Audience Manager的所有資訊？

否，只限在啟用 Audience Manager 對象期間或之後以及在符合區段資格期間或之後造訪您網站之使用者的相關資料。

+++

+++ 這可提供每個區段的可定址對象總數嗎？

不一定。您可得知在符合區段資格期間或之後來到您網站的該區段訪客數。

+++

+++ 這跟連到Analytics的舊版Cookie目的地有何不同？

區段是符合資格且在同一點選中即時傳回。 系統會自動顯示易記名稱。

+++

+++ 如果我的某些報表套裝中含有個人資料，而其他沒有，該怎麼辦？&lt;

提示：建立兩個目標──將個人資料報表套裝新增至一個目標，並將沒有個人資料的報表套裝新增至另一個目標。

+++

## Analytics 專屬常見問答 {#aa-specific}

+++ 此整合在Analytics中會以維度還是區段形式顯示？

以維度形式：「對象ID」和「對象名稱」。

+++

+++在Analytics中，可以在哪裡使用這些維度？

任何地方；這些維度的處理方式與在Analytics中收集的任何其他維度相同。

+++

+++ 在Analytics中為何看不到資料流入？

資料來源和目的地之間很可能存在Adobe Audience Manager隱私權控制衝突。

+++

+++ 即使我已選擇傳送所有區段，為何在Analytics中仍會遺失部分割槽段？&lt;

* 目的地和區段資料來源中的Adobe Audience Manager資料匯出控制可能有衝突，使得某些區段無法傳送。

* 若您在區段中使用了協力廠商資料特徵，則這些區段無法與包含個人資料的目的地 (一組報表套裝) 共用。

+++

+++ 我的Analytics報表中為何顯示「已達對象上限」？ (注意：這也會在Data Warehouse中呈現為「對象ID = -1」和`::max_audiences_exceeded::`)

根據預設，Adobe Audience Manager的Audience Analytics整合會將訪客符合資格的所有區段依每次點選傳送至Analytics。 如果訪客在一次點選中屬於超過150個Adobe Audience Manager區段，系統會將最近符合資格的&#x200B;**150個區段**&#x200B;傳送至Analytics，其餘清單則會截斷。 系統會傳送額外標幟給 Analytics，表示細分群體清單已遭截斷，並在「客群名稱」維度中顯示為「已達客群上限」，在「客群 ID」維度中則會顯示「-1」。

雖然訪客不太可能在特定的點擊中符合超過 150 個區段，但偶然情況下也可能會發生。如果報告中出現「已達客群上限」，您有兩種因應方式：

* 選項1：繼續讓整合工作以立即可用狀態作業，對特定訪客傳送最新的150個合格區段。

* 選項2：在Adobe Audience Manager中，選擇對您業務而言最重要的150個區段進行整合。 Adobe Audience Manager接著只會針對這150個區段檢查訪客。 此方法的缺點是，在所有訪客中，您僅能收到這 150 個區段。換句話說，由於整合的按點擊性質，「選項 1」方法可以提供無限區段。

+++

+++ 為了進行整合，Analytics是否需要為額外的伺服器呼叫付費？

否。Adobe Audience Manager受眾會整合至Analytics點選伺服器端。 這不會導致 Analytics (主要或次要) 的額外伺服器呼叫。

+++

## 伺服器端轉送 (SSF) 常見問答 {#SSF}

+++ 如果我已實作舊式SSF，我是否還需要前往Analytics「管理控制檯」並開啟報表套裝SSF？

是。在Adobe Audience Manager目的地設定中，您只會看到已開啟SSF的報表套裝。

+++

+++ 為什麼我無法在Analytics「管理控制檯」中開啟某些報表套裝的SSF？

您只能啟用對應至 Experience Cloud 組織的套裝。

如需更多此主題的常見問答，請參閱[伺服器端轉送常見問答](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf-faq.md)。

+++

## 一般常見問答 {#section_E55410BBFB624AAFB87ADCF7F036DDA3}

+++ Audience Manager和Analytics之間的區段訪客計數為何不同？

檢視[訪客計數差異](/help/integrate/c-audience-analytics/visitor-count-reconciliation.md)。

+++

+++ Adobe Audience Manager中的「對象」與Analytics中的「區段」有何不同？

請參閱[瞭解Analytics和Audience Manager中的區段](/help/integrate/c-audience-analytics/aam-analytics-segments.md)。 Adobe Audience Manager對象會傳送並共用為「維度」元件，以用於Analytics。 舉例來說，區段不會在「區段產生器」中顯示為區段，但會顯示為維度，供您建立區段。

+++

+++ 從Adobe Audience Manager整合的客戶屬性和客戶資料有何不同？

客戶屬性不是以時間為基礎；可回溯套用並前進。 Adobe Audience Manager整合資料以時間為基礎，僅支援未來發展。 此外，客戶屬性是Experience Cloud訪客ID的查詢表，而Adobe Audience Manager整合則是將訪客的資料彙整至每個點選中。

+++

+++ 對於此問題的舊版方法（例如舊的測試版或「諮詢」外掛程式Cookie目的地）有何影響？

我們建議您實施作業新的整合，並刪除舊目的地。

+++
