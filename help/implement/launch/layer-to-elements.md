---
description: 'null'
title: 將資料層物件對應至資料元素
uuid: null
translation-type: tm+mt
source-git-commit: 283fcd5832abe4c09caa332c2ebc3a22029e6707

---


# 將資料層物件對應至資料元素


為實 [作建立資料層](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html) ，您可以將其中的物件對應至Launch中 [的資料元素](https://docs.adobe.com/content/help/en/launch/using/reference/manage-resources/data-elements.html#create-a-data-element)。 資料元素是您資料圖的建置區塊，可透過多種方式加以運用。 您可以使用資料元素跨Adobe Platform解決方案收集、組織和傳遞資料，包括您的Analytics報表。

要將資料層對象映射到啟動資料元素：

1. 在啟動中，按一下您要新增資料元素的屬性名稱。 如果您尚未設定屬性，請參閱「建立啟動屬 [性」的指示](https://docs.adobe.com/content/help/en/core-services-learn/implementing-in-websites-with-launch/configure-launch/launch.html)。

2. Click **Data Elements** and then click **Create New Data Element**.

   ![建立資料元素](assets/createelement.png)


3. 輸入您的資料元素名稱。 此名稱應是與您要追蹤之資料層中JavaScript變數相對應的簡單標籤。

4. 對於「擴充功能」，請選取「 **核心」。** 此擴充功能包含您需要的所有變數。

5. For **Data Element Type**, select **JavaScript Variable**. 在適用 **欄位中輸入** Javascript變數名稱。 這應符合JavaScript資料層中物件的確切名稱。

6. 在「 **預設值**」中，輸入預設情況下要建立的任何值，或將其保留為空（如果適用）。

7. 根據您的做法，您可以選擇強制小寫值並強制執行乾淨文本的選項（「啟動」將應用常規間距）。

8. 指定您要為新資料元素具有「啟動儲存區」值的持續時間。

9. 按一下&#x200B;**「儲存」**。

下列範例顯示在Launch中為資料層中的JavaScript變數建立的「頁 ``pageName`` 面名稱」資料元素：

![指定元素](assets/new_element.png)


您的資料層物件會對應至資料元素，您可以運用這些物件來填入Analytics變數。 如需詳細資訊，請參 [閱將資料元素對應至Analytics變數](https://docs.adobe.com/content/help/en/analytics/implementation/prepare/data-layer.html)。
