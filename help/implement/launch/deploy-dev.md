---
title: 將 Adobe Analytics 部署至開發環境
description: 了解如何使用標記將 Adobe Analytics 部署至您的開發環境。
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: ea6812c8e596773abb8a05bbdb37bc641967c9b8
workflow-type: ht
source-wordcount: '594'
ht-degree: 100%

---

# 將 Analytics 實作部署至開發環境

當您已建立及設定標記屬性後，就表示資料庫已準備好可以部署並在您的網站上實作程式碼。

>[!NOTE]
>Adobe Experience Platform Launch 已經過品牌重塑，現在是 Experience Platform 中的一套資料收集技術。 因此，所有產品文件中出現了幾項術語變更。 如需術語變更的彙整參考資料，請參閱以下[文件](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)。

## 先決條件

[為 Adobe Analytics 建立及設定標記屬性](create-analytics-property.md)：存取此工具，並建立 Analytics 實作的空間。

## 建立轉接器和環境

標記可在部署程式碼時配合許多組織工作流程的需求。 請按照下列步驟，為 Analytics 實作建立最少的必要元件。 您身為標記管理員，可以在組織內工作，以建立用來部署 Adobe 解決方案的正確工作流程。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下您打算在您的網站上實作的標記屬性。
3. 按一下轉接器標記，然後按一下「新增轉接器」。
4. 將其命名為「Akamai」，然後在類型下拉式選單中選取 Akamai。按一下「儲存」。
5. 前往環境標記，然後按一下「建立新環境」。
6. 選取開發，將其命名「開發環境」，然後從下拉式選單中選取 Akamai 轉接器。按一下建立，然後按一下關閉。
7. 按一下新增環境，選取測試，將其命名為測試環境，然後選取 Akamai 轉接器。按一下建立，然後按一下關閉。
8. 再次按一下新增環境，選取生產，將其命名為「生產環境」，然後選取 Akamai 轉接器。按一下建立，然後按一下關閉。

## 建立開發資料庫

儘管目前所做的所有變更和設定，但其實尚未發佈任何程式碼。建立資料庫 (大略轉譯為變更集合) 可讓您發佈要用於網站上的程式碼。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下您打算在您的網站上實作的標記屬性。
3. 按一下發佈標記，然後按一下「新增資料庫」。
4. 將資料庫命名為「初始變更」，然後選取開發環境。
5. 按一下新增所有變更的資源，這會自動列出 Adobe Analytics、Identity Service 和 Core。
6. 按一下「儲存」。
7. 回到發佈工作流程畫面，按一下新資料庫旁邊的下拉式選單，然後按一下開發建置。幾秒後，資料庫上的黃色圓點會變成綠色，表示建置成功。
8. 前往環境標記，然後按一下「開發環境」。
9. 在「安裝標記」底下，複製程式碼區塊，並將其提供給貴組織的網站負責人。

## 在您網站的開發環境中安裝標記

如果您可控制網站的程式碼，請在網站的每個頁面的個別位置中實施程式碼的兩個區塊 (在 `<head>` 標記中以及結尾 `</body>` 標記的正上方)。此程式碼通常會放置在網站的普遍範本中。僅包含實作程式碼的空白頁面看起來類似以下內容：

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

**嘗試建置失敗。**

常見的原因是，元素已經存在於其他推送至測試環境或生產環境的資料庫中。一開始建立資料庫時，請確保僅將已變更的資源新增至資料庫。

## 文件和其他資源

- [快速入門指南](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=en)：學習標記實作的基本工作流程
- [發佈總覽](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en)：了解更多有關發佈與環境的資訊

## 後續步驟

[驗證 Analytics 實作並發佈至生產環境](validate-publish-prod.md)：開始取得 Adobe Analytics 中的值。
