---
title: 將 Adobe Analytics 部署至開發環境
description: 了解如何使用標記將 Adobe Analytics 部署至您的開發環境。
feature: Tags
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '587'
ht-degree: 92%

---

# 將 Analytics 實作部署至開發環境

當您已建立及設定標記屬性後，就表示資料庫已準備好可以部署並在您的網站上實作程式碼。

## 先決條件

[為 Adobe Analytics 建立及設定標記屬性](create-analytics-property.md)：存取此工具，並建立 Analytics 實作的空間。

## 建立轉接器和環境

標記可在部署程式碼時配合許多組織工作流程的需求。 請按照下列步驟，為 Analytics 實作建立最少的必要元件。 您身為標記管理員，可以在組織內工作，以建立用來部署 Adobe 解決方案的正確工作流程。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下您打算在您的網站上實作的標記屬性。
3. 按一下&#x200B;**[!UICONTROL 主機]**，然後按一下&#x200B;**[!UICONTROL 新增主機]**。
4. 將其命名為`"Adobe managed"`，並在型別下拉式清單中選取&#x200B;**[!UICONTROL 由Adobe管理]**。 按一下「儲存」。
5. 瀏覽至&#x200B;**[!UICONTROL 環境]**，然後按一下&#x200B;**[!UICONTROL 新增環境]**。
6. 選取&#x200B;**[!UICONTROL 開發]**，將其命名為`"Dev Environment"`，然後從下拉式清單中選取Adobe管理主機。 按一下&#x200B;**[!UICONTROL 儲存]**。
7. 將出現一個顯示網頁版安裝說明的模型視窗。我們將在稍後再返回這個視窗；現在請按一下&#x200B;**[!UICONTROL 關閉]**。
8. 按一下&#x200B;**[!UICONTROL 新增環境]**，選取&#x200B;**[!UICONTROL 中繼環境]**，將其命名`"Staging Environment"`，然後選取 Adobe 管理主機。按一下&#x200B;**[!UICONTROL 建立]**，然後關閉安裝說明模型視窗。
9. 按一下&#x200B;**[!UICONTROL 新增環境]**，再度選取&#x200B;**[!UICONTROL 生產環境]**，將其命名`"Production Environment"`，然後選取 Adobe 管理主機。按一下&#x200B;**[!UICONTROL 建立]**，然後關閉安裝說明模型視窗。

## 建立開發資料庫

儘管目前所做的所有變更和設定，但其實尚未發佈任何程式碼。建立資料庫 (大略轉譯為變更集合) 可讓您發佈要用於網站上的程式碼。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
2. 按一下您打算在您的網站上實作的標記屬性。
3. 按一下&#x200B;**[!UICONTROL 發佈流程]**&#x200B;索引標籤，然後按一下&#x200B;**[!UICONTROL 新增資料庫]**。如需有關本頁面的更多資訊，請參閱標記文件中的[發佈概觀](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=zh-Hant)。
4. 為資料庫命名`'Initial changes'`，並選取您的開發環境。
5. 按一下&#x200B;**[!UICONTROL 新增所有變更的資源]**，這會自動列出 Adobe Analytics、身分識別服務以及核心。
6. 按一下&#x200B;**[!UICONTROL 儲存]**。
7. 回到發佈工作流程畫面，按一下新程式庫旁邊的下拉式清單，然後按一下&#x200B;**[!UICONTROL 開發建置]**。 過了一會兒，資料庫上的黃色圓點會變成綠色，表示建置成功。
8. 瀏覽至&#x200B;**[!UICONTROL 環境]**，然後按一下您的開發環境右邊的安裝圖示。這個動作會再度開啟網頁版安裝說明的模型視窗。
9. 複製程式碼區塊，並將其提供給貴組織的網站負責人。

## 在您網站的開發環境中安裝標記

如果您控制您網站的程式碼，請在各自的位置實作每個程式碼區塊：

* 主標記屬於您網站的 `<head>` 標記。
* 如果您選擇同步載入標記，您還必須在網站的關閉`</body>`標記下方包含一個次要程式碼區塊。您可以透過切換網頁版安裝說明中的&#x200B;**[!UICONTROL 以非同步方式載入資料庫]**&#x200B;選項來選擇同步載入資料庫標記。

標記程式碼通常會被放置在網站的總體範本中。僅包含實作程式碼的空白頁面看起來類似以下內容：

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <title>Example page</title>
  <script src="//assets.adobedtm.com/launch-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx-development.min.js"></script>
</head>
<body>
   <p>This is a test page.</p>
   <!-- Only include this extra code if you load tags synchronously -->
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## 疑難排解

**嘗試建置失敗。**

常見的原因是，元素已經存在於其他推送至測試環境或中繼環境的資料庫中。一開始建立資料庫時，請確保僅將已變更的資源新增至資料庫。

## 後續步驟

[驗證 Analytics 實作並發佈至生產環境](validate-publish-prod.md)：開始取得 Adobe Analytics 中的值。
