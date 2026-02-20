---
title: visitorID
description: 使用自訂訪客 ID。
feature: Appmeasurement Implementation
exl-id: cb336042-01a1-4a66-a947-a221a7919c1b
role: Admin, Developer
source-git-commit: de98bf68c57f5453b6662f6e6e57312d8fd3e642
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 19%

---

# visitorID

Adobe使用數種不同的方法來[識別您網站上的訪客](../../id/overview.md)。 **`visitorID`變數會覆寫其他所有訪客識別方法。**

>[!IMPORTANT]
>
>Adobe 建議您不要使用此變數。請改用 [Adobe Experience Cloud 身分識別服務](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=zh-Hant)。

## Analytics如何使用`visitorID`

此變數是手動訪客ID覆寫，可取代所有其他形式的訪客身分識別。 若要計為單一訪客，個人的每次點選都必須使用相同的`visitorID`值。

* 省略`visitorID`的點選會退回給其他訪客識別方法，並視為個別訪客。
* 使用多個`visitorID`值的點選會被視為個別訪客。
* Adobe不會將使用不同訪客ID的點選拼接在一起。

請參閱Adobe Analytics中的[訪客身分識別](../../id/overview.md)，以取得身分識別優先順序的詳細資訊，以及混合識別碼可能會誇大訪客計數的原因。

>[!WARNING]
>
>設定`visitorID`，前提是您可以保證該人員每次點選時都設定此值，而且值絕不會變更。 僅在某些點選上設定它，在瀏覽途中引入（例如驗證），或在點選之間變更它，會將單一訪客的活動分割成多個訪客。

>[!CAUTION]
>
>無效的自訂訪客ID值可能會導致資料不正確，並造成報告效能不佳。 如果此變數包含預設或預留位置值（例如`"0"`或`"NULL"`），Adobe會將這些點選視為相同的訪客。 此情況會導致資料不正確、人為降低訪客計數，以及訪客層級區段無法如預期運作。 不當實作的自訂訪客ID也會對處理伺服器造成大量負載、增加[延遲](/help/technotes/latency.md)並降低報表效能。

## 使用Adobe Analytics擴充功能的訪客ID

「[!UICONTROL 訪客 ID]」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL Cookie]」摺疊式功能表下方的欄位。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 選取所需的標籤屬性。
3. 移至[!UICONTROL 擴充功能]標籤，然後選取Adobe Analytics底下的&#x200B;**[!UICONTROL 設定]**&#x200B;按鈕。
4. 展開[!UICONTROL 「Cookie」]摺疊式功能表，如此可顯示[!UICONTROL 「訪客 ID」]欄位。

將此欄位指派給包含自訂訪客 ID 的資料元素。**請勿將此欄位設為所有訪客的單一靜態值。**&#x200B;使用會針對每位訪客解析並在所有點選中保持不變的資料元素。

## AppMeasurement和Analytics擴充功能自訂程式碼編輯器中的s.visitorID

`s.visitorID` 變數是包含訪客自訂唯一識別碼的字串。有效值包括最多100個位元組的英數字元。 請避免在此變數中使用虛線、空格、底線或符號。

```js
s.visitorID = "abc123";
```

## 使用網頁SDK的訪客ID

Adobe Experience Platform Edge Network可讓您使用XDM的[身分對應](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/overview.html?lang=zh-Hant#using-identitymap)來提供多個識別碼。 「身分對應」中的每個身分都有不同的名稱空間。 您可以在[資料流組態](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=zh-Hant#analytics)中，指定應該用於訪客ID的名稱空間。 設定此欄位後，當您傳送具有為此名稱空間指定的值的事件時，系統會自動將其用作Analytics中的訪客ID。
