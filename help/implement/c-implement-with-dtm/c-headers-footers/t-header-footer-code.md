---
description: 使用動態標籤管理來新增頁首與頁尾代碼，以決定網站上 JavaScript 和頁面內容的載入方式。無論使用哪個託管選項，您都必須在網站的每個頁面上安裝頁首與頁尾代碼。
keywords: Analytics實作；實施方法；動態標籤管理；dtm；程式碼；頁面程式碼；頁首代碼；頁尾代碼；內嵌代碼；內嵌索引標籤；內嵌內嵌
seo-description: 使用動態標籤管理來新增頁首與頁尾代碼，以決定網站上 JavaScript 和頁面內容的載入方式。無論使用哪個託管選項，您都必須在網站的每個頁面上安裝頁首與頁尾代碼。
seo-title: 新增頁首與頁尾代碼
solution: Analytics
title: 新增頁首與頁尾代碼
topic: 開發人員和實施
uuid: 23d89ae0-340a-4b12-91d1-953b4613c98e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 新增頁首與頁尾代碼

使用動態標籤管理來新增頁首與頁尾代碼，以決定網站上 JavaScript 和頁面內容的載入方式。無論使用哪個託管選項，您都必須在網站的每個頁面上安裝頁首與頁尾代碼。

因為動態標籤管理會同時在頁首與頁尾中加入代碼片段，所以您可以在頁面開始或結束的位置執行規則。此功能可讓您實施測試工具和其他技術，並同時繼續控制對頁面的追蹤。

動態標籤管理會建立測試和生產內嵌代碼，您可以在將變更推送至生產環境之前，用來在您的測試環境測試您的變更。

>[!IMPORTANT]
>
>為了成功實施，您必須依照Adobe說明中出現的這些指示進行。Specifically, you must place the header code in the `<head>` section of your document templates. Also, you must place the footer code just before the closing `</body>` tag. 將這兩個內嵌代碼中的一個放置在標記中，或使用非同步方法來附加內嵌代碼，或是使用任何方式包裝內嵌代碼，均&#x200B;*不是*&#x200B;受支援的動態標籤管理實施方式。內嵌代碼必須依所提供明確實施。
>
>不受支援的實作會造成非預期的結果，因而使得客戶服務和工程人員無法協助您進行實作。

1. 在動態標籤管理介面中，開啟[!UICONTROL 「內嵌」]標籤，並選取託管選項 (例如 Akamai)，然後將其切換至「啟用」。

   步驟結果1.複製動態標籤管理在「內嵌」標籤中提供的生產頁首代碼，並將其放置在網站 HTML 的 [!DNL HEAD] 區段內。

   ![](assets/dtm-embed.png)

   Place the code as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">]標籤的位置。正式生產網站的每個頁面上都應放置此代碼片段。

   >[!NOTE]
   >
   >Production embed code reflects only the published items in that [property](../../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123). 不過，用於測試的內嵌代碼會反映關聯的屬性中的所有項目，而不論狀態為已發佈或已取消發佈。若要在生產網站上測試取消發佈的項目，請在本機的主控台中啟用測試，請遵循此文件中的指示 [測試 Akamai 託管的取消發佈規則](../../../implement/c-implement-with-dtm/c-rules/t-test-rules-akamai.md#task_B397167F9E9B4487957AD6CE2AD47259).

1. 複製生產頁尾代碼，並將它放置在網站 HTML 的 [!DNL BODY] 區段內。

   Place the code as close to the [!DNL </body>]標籤的位置。
1. 複製測試頁首與頁尾代碼，然後在您的測試網站上重複上述步驟。

   >[!NOTE]
   >
   >The difference between production and staging code snippets is the addition of [!DNL -staging] to the filename in the staging version. 頁尾代碼在測試與生產版本中維持不變。

