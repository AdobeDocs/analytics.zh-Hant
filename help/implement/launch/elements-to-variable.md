---
description: 'null'
title: 將資料元素對應至Analytics變數
uuid: null
translation-type: tm+mt
source-git-commit: bb9648f4886ac26c77d89f850f7a68d40a9b4ffc

---


# 將啟動資料元素對應至Analytics變數


將資 [料層物件對應至啟動資料元素後](https://docs.adobe.com/content/help/en/analytics/implementation/layer-to-elements.md)，您可以將資料元素對應至 [Analytics變數](https://docs.adobe.com/content/help/en/analytics/implementation/vars/overview.html)。

若要將啟動資料元素對應至Analytics變數：

1. 如果適用，請將資料元素指派給全域變數。 某些資料元素(例如「頁 *面名稱* 」)會套用至屬性上的每個頁面。 在此類情況下，您可以執行下列動作，以全域設定變數：

2. 在Launch中，向下捲動並按一下 **Extensions Catalog**。

   ![擴充功能目錄](assets/extensions.png)

3. 按一 **下「Analytics** 」下的「設定」。

   ![Analytics 擴充功能](assets/configure.png)


4. 在「 **全域變** 數 **」中的eVar**&#x200B;下 [](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html) ，選取您已設定要與變數關聯的eVar。 選 **取「設為**」，然後按一下最右側欄位中的桶圖示，以指定資料元素。

   ![指定eVar](assets/evars.png)

5. 在「選 **取資料元素** 」快顯視窗中，選取您要套用至變數的資料元素。

6. 按一下&#x200B;**「儲存」**。


或者，如果資料元素與全域變數沒有關聯，您只需建立 [規則](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/processing-rules/processing-rules.html) ，將資料元素指派給prop或evar。
