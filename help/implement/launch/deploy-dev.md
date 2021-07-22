---
title: 將 Adobe Analytics 部署至開發環境
description: 了解如何使用標籤將Adobe Analytics部署至開發環境。
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: 9b9a338e3652c85ae0f8ce79b98a2babf427ab4c
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 63%

---

# 將 Analytics 實作部署至開發環境

建立並設定標籤屬性後，即可部署程式庫，並在您的網站上實作程式碼。

>[!NOTE]
>Adobe Experience Platform Launch已重新命名為Experience Platform中的資料收集技術套件。 因此，產品檔案中已推出數個術語變更。 有關術語更改的綜合參考，請參閱以下[document](https://experienceleague.adobe.com/docs/experience-platform/tags/term-updates.html?lang=en)。

## 先決條件

[建立並設定Adobe Analytics的標籤屬性](create-analytics-property.md):存取工具並為Analytics實作建立空間。

## 建立轉接器和環境

標籤可在部署程式碼時配合許多組織工作流程。 請按照下列步驟，為 Analytics 實作建立最低必要元件。身為標籤管理員，您可以在組織內工作，為部署Adobe解決方案建立正確的工作流程。

1. 前往 [Adobe Experience Platform Launch](https://launch.adobe.com)，然後在出現提示時登入。
2. 按一下您要在網站上實作的標籤屬性。
3. 按一下轉接器標籤，然後按一下「新增轉接器」。
4. 將其命名為「Akamai」，然後在類型下拉式選單中選取 Akamai。按一下「儲存」。
5. 前往環境標籤，然後按一下「建立新環境」。
6. 選取開發，將其命名「開發環境」，然後從下拉式選單中選取 Akamai 轉接器。按一下建立，然後按一下關閉。
7. 按一下新增環境，選取測試，將其命名為測試環境，然後選取 Akamai 轉接器。按一下建立，然後按一下關閉。
8. 再次按一下新增環境，選取生產，將其命名為「生產環境」，然後選取 Akamai 轉接器。按一下建立，然後按一下關閉。

## 建立開發程式庫

儘管目前所做的所有變更和設定，但其實尚未發佈任何程式碼。建立程式庫 (大略轉譯為變更集合) 可讓您發佈要用於網站上的程式碼。

1. 前往 [Adobe Experience Platform Launch](https://launch.adobe.com)，然後在出現提示時登入。
2. 按一下您要在網站上實作的標籤屬性。
3. 按一下發佈標籤，然後按一下「新增程式庫」。
4. 將程式庫命名為「初始變更」，然後選取開發環境。
5. 按一下新增所有變更的資源，這會自動列出 Adobe Analytics、Identity Service 和 Core。
6. 按一下「儲存」。
7. 回到發佈工作流程畫面，按一下新程式庫旁邊的下拉式選單，然後按一下開發建置。幾秒後，程式庫上的黃色圓點會變成綠色，表示建置成功。
8. 前往環境標籤，然後按一下「開發環境」。
9. 在「安裝標籤」下，復製程式碼區塊並提供給組織的網站擁有者。

## 在您網站的開發環境中安裝標籤

如果您可控制網站的程式碼，請在網站的每個頁面的個別位置中實施程式碼的兩個區塊 (在 `<head>` 標籤中以及結尾 `</body>` 標籤的正上方)。此程式碼通常會放置在網站的普遍範本中。僅包含實作程式碼的空白頁面看起來類似以下內容：

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

常見的原因是，元素已經存在於其他推送至測試環境或生產環境的程式庫中。一開始建立程式庫時，請確保僅將已變更的資源新增至程式庫。

## 文件和其他資源

- [快速入門手冊](https://experienceleague.adobe.com/docs/experience-platform/tags/get-started/quick-start.html?lang=en):了解標籤實作的基本工作流程
- [發佈概述](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html?lang=en):進一步了解發佈和環境

## 後續步驟

[驗證 Analytics 實作並發佈至生產環境](validate-publish-prod.md)：開始取得 Adobe Analytics 中的值。
