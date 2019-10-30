---
description: '[!DNL Activity Map]中連結追蹤的常見問題。'
seo-description: '[!DNL Activity Map]中連結追蹤的常見問題。'
seo-title: 連結追蹤常見問題集
solution: Analytics
title: 連結追蹤常見問題集
topic: Activity Map
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
translation-type: tm+mt
source-git-commit: ae18932eda59c059e2aa635cc30f233b88840031

---


# 連結追蹤常見問題集

Frequently asked questions about link tracking in [!DNL Activity Map].

> [!CAUTION] 開啟追蹤 [!DNL Activity Map] 後， **您可能會收****集個人識別資訊(PII)資料。**&#x200B;此資料可以單獨使用，或搭配其他資訊使用，藉以識別、聯絡或尋找個別人員，或者識別環境中的個人。

Here are some known cases where PII data might be collected using [!DNL Activity Map] Tracking:

* `Mailto` 連結。 Mailto 連結是一種 HTML 連結，它會啟用電腦上的預設郵件用戶端來傳送電子郵件。
* `User ID` 當使用者登入後，網站的頁首／頁尾中可能會顯示的連結。
* 若為金融機構，帳號可能會以連結的型態顯示。按一下連結，就可以收集該連結的文字。
* 醫療照護網站也可能讓 PII 資料以連結的型態顯示。按一下這些連結，就可以收集該連結的文字，從而收集 PII 資料。

<table id="table_0951EAC617344156BAE43000CCD838AF"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <b>問: 什麼時候會發生連結追蹤?</b> <p> </p> </td> 
   <td colname="col2"> 答：[!DNL Activity Map]連結和區域識別是當使用者按一下頁面時發生的。 </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>問: 預設會追蹤哪些項目?</b> <p> </p> </td> 
   <td colname="col2"> 答: 如果點按事件發生在元素上，元素必須傳遞一些檢查以判斷 AppMeasurement 是否將其視為連結。所進行的檢查如下: 
    <ul id="ul_81B9A5A7F8534E71AEF68F2199A154F0"> 
     <li id="li_49F6DDD9DC124AE5846EC5B7D7BEA20E">是不是具有 HREF 屬性的 &lt;A&gt; 或 &lt;AREA&gt; 標記? </li> 
     <li id="li_77828D24D54343E5B9A1FF7345221781">是否有點按上屬性且設定 s_objectID 變數? </li> 
     <li id="li_D4B0AEEEA58A4F82A1BCBD3971A60D02">這是否為 INPUT 標記或具有值或子文字的 SUBMIT 按鈕? </li> 
     <li id="li_F7ABE88308E1413E9B9C2224DEC91BAB">這是否為具有類型 IMAGE 和 src 屬性的 INPUT 標記? </li> 
     <li id="li_F34A0C986E8040109A1DDF88C26E56D5">這是否為 &lt;Button&gt;? </li> 
    </ul> <p>如果以上任一問題的答案為<b>是</b>，則會將該元素視為連結，並進行追蹤。 </p> <p>重要: AppMeasurement 不會將具有屬性 type="button" 的按鈕標記視為連結。請考慮移除按鈕標記上的 type="button"，改為新增 role="button" 或 submit="button"。 </p> <p>重要：以"#"開頭的href為錨記，AppMeasurement會將其視為內部目標位置，而非連結（因為您未離開頁面）。預設情況下，[!DNL Activity Map]不跟蹤這些內部目標位置。 它只追蹤導覽使用者至新頁面的連結。</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>問：[!DNL Activity Map]如何追蹤其他視覺化HTML元素？</b> </td> 
   <td colname="col2"> 
    <ol id="ol_DA3AED165CFF44B08DFB386D4DEE26C5"> 
     <li id="li_E3E3F498F37B4FADAFDA39CCAE41511F"> <b>透過函 <code> s.tl() </code> 數</b> <p>如果點按是透過s.tl呼叫發生，則[!DNL Activity Map]也會收到此點按事件，並判斷是否找到linkName字串變數。 在s.tl執行期間，該linkName將被設為[!DNL Activity Map]連結ID。 將使用引起 s.tl() 呼叫的被點按元素來判斷地區。範例: </p> <p> 
       <code>
         &lt;img&amp;nbsp;onclick="s.tl(true,'o','abc')"&amp;nbsp;src="someimageurl.png"/&gt; 
       </code> </p> </li> 
     <li id="li_A93725B810FE408BA5E6B267CF8CEAE5"> <b>透過變 <code> s_objectID </code> 數</b> <p>範例: </p> <p> 
       <code>
         &lt;img&nbsp;onclick="s_objectID='abc';"&nbsp;src="someimageurl.png"/&gt; &lt;a&nbsp;href="some-url.html"&nbsp;onclick="s_objectID='abc';"&nbsp;&gt;Link&nbsp;Text&nbsp;Here&lt;/a&gt;
       </code> </p> <p>重要： 請注意，在[!DNL Activity Map]中使用s_objectID時，需要結尾分號(;)。 </p> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>問: 可以提供一些會被追蹤的連結範例嗎?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_697E5CE0B84D4A309DD80670697A02BA"> 
     <li id="li_2C511EFD10F14F438B1F3A1BAB4B45E0"> 
      <code>
        &lt;a&amp;nbsp;href="/home"&gt;Home&lt;/a&gt; 
      </code> </li> 
     <li id="li_76F3DB36ED734132A2386871E6EB4929"> 
      <code>
        &lt;input&amp;nbsp;type="submit"&amp;nbsp;value="Submit"/&gt; 
      </code> </li> 
     <li id="li_10CF9EDA224645169E7CDF74956DB98B"> 
      <code>
        &lt;input&amp;nbsp;type="image"&amp;nbsp;src="submit-button.png"/&gt; 
      </code> </li> 
     <li id="li_9FA171D7F49547E798DE21869F73A402"> 
      <code>
        &lt;p&nbsp;onclick="var&nbsp;s_objectID='custom&nbsp;link&nbsp;id';"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_C5D77589006E4514AA6F3AEB509A0BAF"> 
      <code>
        &lt;div&nbsp;onclick="s.tl(true,'o','custom&nbsp;link&nbsp;id')"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/div&gt;
      </code> </li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b>問: 可以提供一些「不會」被追蹤的連結範例嗎?</b> </td> 
   <td colname="col2"> 
    <ol id="ol_CDFDB572F76B4F68A64B66A6B0237547"> 
     <li id="li_99372060646B43EF94C13A9C682CE693">原因: 錨記沒有有效的 href 
      <code>
        &lt;a&amp;nbsp;name="innerAnchor"&gt;Section&amp;nbsp;header&lt;/a&gt; 
      </code> </li> 
     <li id="li_736A5F7DC2D74B4DA1CECEE3AD10EB19">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;p&nbsp;onclick="showPanel('market&nbsp;rates')"&gt; &nbsp;&nbsp;&nbsp;&nbsp;&lt;span&nbsp;class="title"&gt;Current&nbsp;Market&nbsp;Rates&lt;/span&gt;&lt;span&nbsp; class="subtitle"&gt;1.45USD&lt;/span&gt; &lt;/p&gt;
      </code> </li> 
     <li id="li_45F9ED97140F47F99F8C167BC1DC546F">Reason: Neither <code> s_ObjectID </code> nor <code> s.tl() </code> present 
      <code>
        &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="A"/&gt; &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="B"/&gt; &lt;input&nbsp;type="radio"&nbsp;onclick="changeState(this)"&nbsp;name="group1"&nbsp;value="C"/&gt;
      </code> </li> 
     <li id="li_9EBFCC58F3A94F30BA62156F14B15D55">原因: src 屬性遺失表單輸入元素 
      <code>
        &lt;input&amp;nbsp;type="image"/&gt; 
      </code> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>
