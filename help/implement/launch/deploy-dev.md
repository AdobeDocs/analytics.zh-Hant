---
title: 將 Adobe Analytics 部署至開發環境
description: 瞭解如何使用 Adobe Experience Platform Launch 來將 Adobe Analytics 部署至開發環境。
translation-type: ht
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# 將 Analytics 實施部署至開發環境

一旦在 Launch 中建立並設定屬性後，即可部署程式庫並在網站上實施程式碼。

## 必要條件

[在 Launch 中為 Adobe Analytics 建立並設定屬性](create-analytics-property.md)：存取此工具並為 Analytics 實施建立空間。

## 建立轉接器和環境

Launch 可在部署程式碼時配合許多組織工作流程。請按照下列步驟，為 Analytics 實施建立最低必要元件。身為 Launch 管理員，您可在組織內努力建立正確工作流程來部署 Adobe 解決方案。

1. 前往 [Adobe Experience Platform Launch](https://launch.adobe.com)，然後在出現提示時登入。
2. 按一下您預計在網站上實施的 Launch 屬性。
3. 按一下轉接器標籤，然後按一下「新增轉接器」。
4. 將其命名為「Akamai」，然後在類型下拉式功能表中選取 Akamai。按一下「儲存」。
5. 前往環境標籤，然後按一下「建立新環境」。
6. 選取開發，將其命名「開發環境」，然後從下拉式功能表中選取 Akamai 轉接器。按一下建立，然後按一下關閉。
7. 按一下新增環境，選取測試，將其命名為測試環境，然後選取 Akamai 轉接器。按一下建立，然後按一下關閉。
8. 再次按一下新增環境，選取生產，將其命名為「生產環境」，然後選取 Akamai 轉接器。按一下建立，然後按一下關閉。

## 建立開發程式庫

儘管目前所做的所有變更和設定，但其實尚未發佈任何程式碼。建立程式庫 (大略轉譯為變更集合) 可讓您發佈要用於網站上的程式碼。

1. 前往 [Adobe Experience Platform Launch](https://launch.adobe.com)，然後在出現提示時登入。
2. 按一下您預計在網站上實施的 Launch 屬性。
3. 按一下發佈標籤，然後按一下「新增程式庫」。
4. 將程式庫命名為「初始變更」，然後選取開發環境。
5. 按一下新增所有變更的資源，這會自動列出 Adobe Analytics、Identity Service 和 Core。
6. 按一下「儲存」。
7. 回到發佈工作流程畫面，按一下新程式庫旁邊的下拉式功能表，然後按一下開發建置。幾秒後，程式庫上的黃色圓點會變成綠色，表示建置成功。
8. 前往環境標籤，然後按一下「開發環境」。
9. 在「安裝 Launch」底下，複製程式碼區塊，然後將其提供給您組織的網站擁有者。

## 將 Launch 安裝在網站的開發環境上

如果您可控制網站的程式碼，請在網站的每個頁面的個別位置中實施程式碼的兩個區塊 (在 `<head>` 標籤中以及結尾 `</body>` 標籤的正上方)。此程式碼通常會放置在網站的普遍範本中。僅包含實施程式碼的空白頁面看起來類似以下內容：

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

- [Launch 快速入門](https://docs.adobe.com/content/help/zh-Hant/launch/using/intro/get-started/quick-start.html)：瞭解 Launch 的基本工作流程
- [Launch 發佈](https://docs.adobe.com/content/help/zh-Hant/launch/using/reference/publish/overview.html)：深入瞭解發佈和環境

## 後續步驟

[驗證 Analytics 實施並發佈至生產環境](validate-publish-prod.md)：開始取得 Adobe Analytics 中的值。
