---
description: Web 屬性可為一或多個具備規則資料庫 (包含在內嵌代碼中) 之網域和子網域的任意分組。
keywords: Analytics Implementation;implementation method;dynamic tag management;dtm;web property;property
title: 建立 Web 屬性
topic: Developer and implementation
uuid: f19d5504-eb44-4d93-a387-7470ab4b3a3a
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 建立 Web 屬性

Web 屬性可為一或多個具備規則資料庫 (包含在內嵌代碼中) 之網域和子網域的任意分組。

>[!NOTE]只有具備管理員權利的使用者才能建立屬性。如需角色的相關詳細資訊，請參閱 Dynamic Tag Management 產品文件中的[在 DTM 中建立及管理群組](https://marketing.adobe.com/resources/help/zh_TW/dtm/groups.html)。

您可以使用DTM管理及追蹤這些資產。 例如，假設您有多個網站是根據一個範本，而您想追蹤所有這些網站上的相同資產。 您可以將一個Web屬性套用至多個網域。

如需有關 Web 屬性和最佳實務的一般資訊，請參閱Dynamic Tag Management 產品文件中的 [Web 屬性](https://marketing.adobe.com/resources/help/zh_TW/dtm/web_property.html)。

1. Navigate to your company page, then click **[!UICONTROL Add Property]**.

   ![](assets/dtm-create-web-property.png)

1. 填寫欄位：

   <table id="table_376D72251C4D4C4CA878D10C18D2532C"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> 元素 </th> 
    <th colname="col2" class="entry"> 說明 </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 名稱</span> </td> 
    <td colname="col2"> <p>屬性的名稱。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> URL</span> </td> 
    <td colname="col2"> <p>屬性的基礎 URL。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 此網站涵蓋多個網域 </span> </td> 
    <td colname="col2"> <p>如果您希望訪客資料在網域之間持續存在，則可新增和移除網域。 如果選取此選項，瀏覽的資料會跨子網域持續存在。 </p> <p>此設定可讓您指定您要如何追蹤在相關子網域或網域之間移動的流量。 子網域的連結會視為對外連結。 子網域的瀏覽會個別追蹤。 </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. （可選）設定 [!UICONTROL Advanced Settings]。

   <table id="table_6E687FBE6ACC4301BCCD837F4DCBB9C9"> 
    <thead> 
    <tr> 
    <th colname="col1" class="entry"> 元素 </th> 
    <th colname="col2" class="entry"> 說明 </th> 
    </tr> 
    </thead>
    <tbody> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 允許多重規則批准</span> </td> 
    <td colname="col2"> <p>允許一次批准此屬性的多個規則。預設僅允許批准單一規則。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 啟用選擇性發佈</span> </td> 
    <td colname="col2"> <p>指定是否允許用戶選擇發佈哪些已批准規則。 這是預設選項。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 追蹤 Cookie 名稱</span> </td> 
    <td colname="col2"> <p>覆寫預設的追蹤 Cookie 名稱。您可以自訂 Dynamic Tag Management 在追蹤您對於接收其他 Cookie 的意願狀態時，所使用的名稱。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 標籤逾時</span> </td> 
    <td colname="col2"> <p>指定逾時和取消標籤要求前，Dynamic Tag Management 等待標籤引發的時間長度。 </p> <p> 由於 Dynamic Tag Management 的運作方式，無須擔心這會是很高的數字。DTM提供有效的方法，以確保緩慢的標籤不會影響使用者體驗。 </p> </td> 
    </tr> 
    <tr> 
    <td colname="col1"> <span class="uicontrol"> 錨點延遲</span> </td> 
    <td colname="col2"> <p>指定在移到下一頁之前，Dynamic Tag Management 會等待標籤在已點按連結上引發的時間長度。預設值為 100 毫秒。 </p> <p>較長的延遲可改善追蹤準確性。Adobe 建議使用 500 毫秒或以內的延遲，使用者對此時間長度不會有感覺。 </p> <p>Dynamic Tag Management 將等候到指定的時間，但如果信標引發更快速，則會將延遲縮短。(也就是說，使用者不會一律等候到延遲的完整時間長度。) </p> </td> 
    </tr> 
    </tbody> 
    </table>

1. 按一下 **[!UICONTROL Create Property]**.
