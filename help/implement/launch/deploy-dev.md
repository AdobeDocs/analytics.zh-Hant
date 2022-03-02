---
title: 將 Adobe Analytics 部署至開發環境
description: 了解如何使用標記將 Adobe Analytics 部署至您的開發環境。
feature: Launch Implementation
exl-id: 324943db-cb0b-40b1-8884-56bb3f608278
source-git-commit: f4b495b11bcbd55bc8448f2c9c09268547fb9750
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 47%

---

# 將 Analytics 實作部署至開發環境

當您已建立及設定標記屬性後，就表示資料庫已準備好可以部署並在您的網站上實作程式碼。

## 先決條件

[為 Adobe Analytics 建立及設定標記屬性](create-analytics-property.md)：存取此工具，並建立 Analytics 實作的空間。

## 建立轉接器和環境

標記可在部署程式碼時配合許多組織工作流程的需求。 請按照下列步驟，為 Analytics 實作建立最少的必要元件。 您身為標記管理員，可以在組織內工作，以建立用來部署 Adobe 解決方案的正確工作流程。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下您打算在您的網站上實作的標記屬性。
3. 按一下 **[!UICONTROL 主機]**，然後按一下 **[!UICONTROL 添加主機]**。
4. 命名它 `"Adobe managed"`，然後選擇 **[!UICONTROL 按Adobe管理]** 的下界。 按一下「儲存」。
5. 導航到 **[!UICONTROL 環境]**，然後按一下 **[!UICONTROL 添加環境]**。
6. 選擇 **[!UICONTROL 開發]**，命名 `"Dev Environment"`，然後從下拉清單中選擇Adobe托管主機。 按一下「**[!UICONTROL 儲存]**」。
7. 出現一個顯示Web安裝說明的模式窗口。 稍後再回到這個窗口，按一下 **[!UICONTROL 關閉]** 暫時。
8. 按一下 **[!UICONTROL 添加環境]**&#x200B;選中 **[!UICONTROL 暫存]**，命名 `"Staging Environment"`，然後選擇Adobe托管主機。 按一下 **[!UICONTROL 建立]**，然後關閉「install instructions modal（安裝說明模式）」窗口。
9. 按一下 **[!UICONTROL 添加環境]** 選擇 **[!UICONTROL 生產]**，命名 `"Production Environment"`，然後選擇Adobe托管主機。 按一下 **[!UICONTROL 建立]**，然後關閉「install instructions modal（安裝說明模式）」窗口。

## 建立開發資料庫

儘管目前所做的所有變更和設定，但其實尚未發佈任何程式碼。建立資料庫 (大略轉譯為變更集合) 可讓您發佈要用於網站上的程式碼。

1. 使用您的 Adobe ID 認證登入[資料收集 UI](https://experience.adobe.com/data-collection)。
2. 按一下您打算在您的網站上實作的標記屬性。
3. 按一下 **[!UICONTROL 發佈流]** ，然後按一下 **[!UICONTROL 添加庫]**。 請參閱 [發佈概述](https://experienceleague.adobe.com/docs/experience-platform/tags/publish/overview.html) 的子菜單。
4. 命名庫 `'Initial changes'`，然後選擇開發環境。
5. 按一下 **[!UICONTROL 添加所有更改的資源]**，它自動列出Adobe Analytics、身份服務和核心。
6. 按一下「**[!UICONTROL 儲存]**」。
7. 返回發佈工作流螢幕，按一下新庫旁邊的下拉清單，然後按一下 **[!UICONTROL 為發展而構建]**。 幾秒鐘後，庫上的黃點變綠，表示生成成功。
8. 導航到 **[!UICONTROL 環境]**，然後按一下開發環境右側的安裝表徵圖。 此操作將再次顯示「Web安裝說明」模式窗口。
9. 複製代碼塊，並將它們提供給您組織的網站所有者。

## 在您網站的開發環境中安裝標記

如果您控制網站的代碼，請在各自的位置實施每個代碼塊：

* 主標籤屬於 `<head>` 在您的站點上標籤。
* 如果選擇同步載入標籤，則還必須在關閉位置正下方包含第二個代碼塊 `</body>` 在您的站點上標籤。 通過切換庫標籤，可以選擇同步載入庫標籤 **[!UICONTROL 非同步載入庫]** 的子菜單。

標籤代碼通常放在站點的總體模板中。 僅包含實作程式碼的空白頁面看起來類似以下內容：

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

常見的原因是，元素已經存在於其他推送至測試環境或生產環境的資料庫中。一開始建立資料庫時，請確保僅將已變更的資源新增至資料庫。

## 後續步驟

[驗證 Analytics 實作並發佈至生產環境](validate-publish-prod.md)：開始取得 Adobe Analytics 中的值。
