---
description: 部署 Analytics 時，請在 Dynamic Tag Management 中使用欄位說明來自訂頁面程式碼。
keywords: Dynamic Tag Management;自訂頁面程式碼;開啟編輯器;執行
seo-description: 部署 Analytics 時，請在 Dynamic Tag Management 中使用欄位說明來自訂頁面程式碼。
seo-title: 自訂頁面程式碼
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 自訂頁面程式碼
uuid: b7cad069-3eb8-4388-b0b0-34f54001e05f
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# 自訂頁面程式碼

部署 Analytics 時，請在 Dynamic Tag Management 中使用欄位說明來自訂頁面程式碼。

新增外掛程式以確保代碼與 Analytics 工具同時執行。如需 Analytics 外掛程式的詳細資訊，請參閱[實施外掛程式](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**[!UICONTROL *`Property`*]** &gt; **[!UICONTROL   ![](assets/settings_gear.png)

編輯工具]** &gt; **[!UICONTROL 自訂頁面程式碼]**

<table id="table_A4676A5FEE814DF9A05DA0E56F8B4C6D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 元素 </th> 
   <th colname="col2" class="entry"> 說明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>開啟編輯器 </p> </td> 
   <td colname="col2"> <p>您可以插入必須在最終 <code>s.t()</code> 呼叫 (包含在 <code>s_code</code> 中) 之前觸發的任何 JavaScript 呼叫。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>執行 </p> </td> 
   <td colname="col2"> <p> <b>UI 設定前</b>: 介面設定優先於自訂代碼 (例如，若介面中已啟用了設定，而您想要覆寫 eVar)。 </p> <p> <b>UI 設定後</b>: 自訂代碼優先於介面設定。 </p> </td> 
  </tr> 
 </tbody> 
</table>

