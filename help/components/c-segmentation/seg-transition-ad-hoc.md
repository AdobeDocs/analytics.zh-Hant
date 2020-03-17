---
description: 如果您習慣使用「Ad Hoc Analysis」中的「區段產生器」，本 FAQ 將說明現有區段和資料夾的變更，以及您需要採取的行動。
keywords: segmentation;segments
title: Ad Hoc Analysis 的轉換指南
topic: Segments
uuid: d409d71a-f8d9-42a2-add2-37d426cd40d1
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Ad Hoc Analysis 的轉換指南

如果您習慣使用「Ad Hoc Analysis」中的「區段產生器」，本 FAQ 將說明現有區段和資料夾的變更，以及您需要採取的行動。

## 功能 {#section_BD58629D1A9346BF879E229FA6BEC7A2}

* 區段在所有報表套裝中都通用。之前，不同的報表套裝使用不同的區段。
* Ad Hoc Analysis 包含對區段產生器的更新，以及區段管理員的完整更新。
* 您現在可以標記區段來進行組織和供稍後搜尋，而不是透過使用資料夾的方式。之前，您是使用資料夾 (在 [!DNL Ad Hoc Analysis] 中) 來組織區段。

## 我現有的區段有什麼改變？{#section_76CF47142D1A4FB6A0718AD9073049FE}

您現有的區段將繼續如往常般運作。任何已套用這些區段的報表都將繼續正常運作。

原本預先定義的區段與套裝區段多半會以區段範本的形式移轉至區段產生器。區段範本的用途是快速建立具有常見對象的自訂區段。區段範本無法直接套用至報表，但可以輕易儲存成自訂區段。

區段範本在「區段產生器」中有特殊的圖示標記。

## 我現有的區段資料夾有什麼改變？{#section_FB04DCF775694E69B761DCA53F301C30}

「區段管理員」不再使用 Ad Hoc Analysis 資料夾，而是使用標記。您的資料夾名稱會自動轉換成標記，而這些標記會套用至對應的區段。

## 已套用區段的已計劃報表有什麼改變？{#section_81D1B215533C46E99E17BAE7A3376FDF}

已計劃的報表會繼續使用您定義的區段正常運作。

當您刪除區段時，已套用此區段的已計劃報表和控制面板會繼續正常運作，亦即區段或控制面板會繼續使用刪除的區段。

## 點擊容器是什麼？它是否與頁面檢視容器不同？{#section_65BBE60A836C4001938830DDA15DC256}

「頁面檢視」容器已重新命名為「點擊」容器，以表示此容器會將所有類型的資料 (而不只是頁面檢視) 分段。例如，連結追蹤呼叫與來自行動 SDK 的 trackAction 呼叫均可在點擊容器中受到納入或排除。

請注意，此容器的運作方式並無改變，只是名稱有變而已。

## 要使用、建立和管理區段需要有什麼權限？{#section_648DFA3A882146C485A84ED014EEC707}

所有使用者均可建立和編輯個人區段。這些區段可直接共用給任何其他 Analytics 使用者。Ad Hoc Analysis 使用者可以看到他們建立的區段以及直接與其共用的區段。

在「統一劃分」Web 主控台中，管理員可以編輯任何區段，並將區段共用給群組以及組織中的每個人。

## 我是否可以看見公司中的所有區段？{#section_AC2D328C7410419E80C7C17971CD95B3}

會顯示您擁有的所有 Ad Hoc Analysis 區段以及專門與您共用的區段。

## 我是否可以在區段管理員中管理所有 Analytics 區段？{#section_AF5EDD72C74A4739BD40C4AF125CE489}

Ad Hoc Analysis 只會顯示您建立的區段或專門與您共用的區段。僅限 Ad Hoc Analysis：您可以使用區段管理員 (組織區段) 來管理臨機分析區段。使用「統一劃分」中的「區段管理員」可以管理所有 Analytics 的區段。

## 有具有相同名稱、但不同定義的重複區段時該怎麼辦？{#section_E2C3A1B4B4274D1B86CAA9C0359D049C}

現在，由於區段可在多個報表套裝中運作，因此您可能發現有多個區段具有相同名稱。建議您採取以下動作之一：

* 重新命名具有相同名稱、但不同定義的區段，或是
* 刪除不再需要的區段。

## Adobe 建議我該如何清理區段？{#section_3AC2D265F9084557A24C6FB39DC6EE49}

* 以 legacy 標記標記所有區段。
* 檢閱您現有的區段。
* 適時將這些區段新增至區段庫。
* 核准要做為標準區段的區段。

## 我為何刪除不了區段？{#section_0FEB6711031A4ABCA915CDA745ECF38D}

如果區段已發佈至 Experience Cloud，則您無法加以刪除或編輯。不過，您可以加以複製再編輯複製的版本。

## 更多關於現有區段會有什麼改變的資訊{#section_83ACAB256F394DCD8B424D8920BDD853}

<table id="table_0AE814A64D2A48ABB28402C4303F420E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 區段類別 </th> 
   <th colname="col2" class="entry"> 這些區段有何變化？ </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ad Hoc Analysis 中的我的最愛區段 </td> 
   <td colname="col2">這些 Ad Hoc Analysis 區段在 Adobe Analytics 中會顯示為一般區段。 <p>不應將它們與「區段管理員」中可讓您將區段標記為我的最愛的「我的最愛」功能混淆。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Ad Hoc Analysis 中的預先設定區段： 
    <ul id="ul_BBF3C3F4D41A40AF98DA9DA6D299AD03"> 
     <li id="li_B65A004BDF8743FDABCD3332AEB8A010">單頁存取次數 </li> 
     <li id="li_908CF5F964154C9D9EBBAC2A900DCB49">來自行動裝置的瀏覽次數 </li> 
     <li id="li_4A715F49AA374463B501D731261A3A4C">來自免費搜尋的瀏覽次數 </li> 
     <li id="li_67CE51237EC34FD4B33942BA14584EBF">來自付費搜尋的瀏覽次數 </li> 
     <li id="li_C3820743178A4E9F9E5E5B5C47401DF2">具有訪客 ID Cookie 的瀏覽次數 </li> 
    </ul> </td> 
   <td colname="col2"> <p>這些區段將會以區段範本的形式移轉至「區段產生器」。 </p> <p>已套用這些區段的現有報表將可繼續正常運作。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1">Experience Cloud (套裝) 區段： 
    <ul id="ul_6968AFF6DEDA4BC8A7885B07CC1F57DF"> 
     <li id="li_073D9496F0C64AEB855855D01E65C1BA">非購買者 </li> 
     <li id="li_8958FD4272A14E16A9AA08216E8BC573">購買者 </li> 
     <li id="li_1436D7C9651D4AC38E10662DEDDD2B95">首次瀏覽次數 </li> 
     <li id="li_69F42B4F6107407792B0014804A8AF7B">來自社交網站的瀏覽次數 </li> 
     <li id="li_29CA111186BE475C943E9F8450BDE8C8">超過 10 分鐘的瀏覽次數* </li> 
     <li id="li_1FEF207959DC4D2E9FC925DD43177AA0">先前造訪過 5 次以上的造訪* </li> 
     <li id="li_219AB1D4FD7E469C9076A23D2CCC7C2C">來自 Facebook 的瀏覽次數* </li> 
    </ul> </td> 
   <td colname="col2"> <p> 這些區段 (具有星號 * 標記者除外) 多半將會以區段範本的形式移轉至「區段產生器」。另外，新增了數個新的區段範本。 </p> <p>已套用這些區段的現有報表將可繼續正常運作。 </p> </td> 
  </tr> 
 </tbody> 
</table>

