---
title: 將Adobe Analytics部署至開發環境
seo-title: 將Adobe Analytics部署至開發環境
description: 瞭解如何使用Adobe Experience Platform Launch將Adobe Analytics部署至您的開發環境。
seo-description: 瞭解如何使用Adobe Experience Platform Launch將Adobe Analytics部署至您的開發環境。
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# 將Analytics實作部署至開發環境

在Launch中建立並設定屬性後，即可部署程式庫並在您的網站上實施程式碼。

## 必備條件

[在Launch中建立及設定Adobe Analytics的屬性](create-analytics-property.md)：存取工具並建立Analytics實作的空間。

## 建立轉換器和環境

Launch可容納許多組織工作流程，以部署程式碼。請遵循下列步驟，建立Analytics實施的最低必要元件。身為Launch管理員，您可以在組織內工作，以建立正確的Adobe解決方案部署工作流程。

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. 按一下您要在網站上實施的Launch屬性。
3. 按一下「轉換器」索引標籤，然後按一下「新增介面卡」。
4. 將其命名為「Akamai」，然後在類型下拉式清單中選取Akamai。按一下「儲存」。
5. 前往「環境」標籤，然後按一下「建立新環境」。
6. 選取「開發」，將其命名為「開發環境」，然後從下拉式清單中選取Akamai介面卡。按一下「建立」，然後按一下「關閉」。
7. 按一下「新增環境」，選取「測試環境」，將其命名為「測試環境」，然後選取Akamai介面卡。按一下「建立」，然後按一下「關閉」。
8. 再次按一下「新增環境」，選取「生產環境」，將其命名為「生產環境」，然後選取Akamai介面卡。按一下「建立」，然後按一下「關閉」。

## 建立開發程式庫

儘管目前已進行所有變更和設定，但尚未實際發佈任何程式碼。建立程式庫(粗略翻譯為一系列變更)可讓您在網站上使用程式碼。

1. Go to [Adobe Experience Platform Launch](https://launch.adobe.com) and log in if prompted.
2. 按一下您要在網站上實施的Launch屬性。
3. 按一下「發佈」索引標籤，然後按一下「新增元件庫」。
4. 命名程式庫的「初始變更」，並選取您的開發環境。
5. 按一下「新增所有變更資源」，自動列出Adobe Analytics、Identity Service和核心。
6. 按一下「儲存」。
7. 回到發佈工作流程畫面，按一下新資料庫旁的下拉式清單，然後按一下「建立開發」。數秒後，資料庫上的黃色點變成綠色，表示建置成功。
8. 前往「環境」標籤，然後按一下您的開發環境。
9. 在「Install Launch」(安裝啓動)底下，複製代碼區塊並將它們提供給您組織的網站擁有者。

## 在您網站的開發環境上安裝Launch

If you control your website's code, implement the two blocks of code in their respective locations (in the `<head>` tag and just above the closing `</body>` tag) on every page of your site. 此程式碼通常放置在網站的覆蓋範本中。僅包含實作代碼的空白頁面看起來如下所示：

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
   <script type="text/javascript">_satellite.pageBottom();</script>
</body>
</html>
```

## 疑難排解

**嘗試建立失敗。**

常見原因是因為其他程式庫中已推送至測試或生產。初始建立程式庫時，請確定只會將已變更的資源新增至程式庫。

## 說明文件與其他資源

- [開始使用Launch](https://docs.adobelaunch.com/getting-started)：瞭解Launch的基本工作流程
- [啓動管理](https://docs.adobelaunch.com/administration)：進一步瞭解轉換器和環境

## 後續步驟

[驗證您的Analytics實作並發佈至生產](validate-publish-prod.md)環境：從Adobe Analytics開始獲取價值。
