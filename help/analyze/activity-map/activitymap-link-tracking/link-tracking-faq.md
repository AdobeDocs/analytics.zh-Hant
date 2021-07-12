---
description: 關於 Activity Map 中連結追蹤的常問問題。
title: 連結追蹤常見問題集
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 44%

---

# 連結追蹤常見問題集

關於 Activity Map 中連結追蹤的常問問題。

>[!CAUTION]
>
>開啟 Activity Map 追蹤功能後，**您就可能會收集個人識別資訊 (PII) 資料。**&#x200B;此資料可以單獨使用，或搭配其他資訊使用，藉以識別、聯絡或尋找個別人員，或者識別環境中的個人。

以下是可能使用 Activity Map 追蹤來收集 PII 資料的一些已知案例：

* `Mailto` 連結。Mailto 連結是一種 HTML 連結，它會啟用電腦上的預設郵件用戶端來傳送電子郵件。
* 當使用者登入後，`User ID` 連結可能會顯示在網站的標題/註腳中。
* 若為金融機構，帳號可能會以連結的型態顯示。按一下連結，就可以收集該連結的文字。
* 醫療照護網站也可能讓 PII 資料以連結的型態顯示。按一下這些連結，就可以收集該連結的文字，從而收集 PII 資料。

## 什麼時候會發生連結追蹤？

Activity Map點按頁面時，就會發生連結和地區識別。

## 預設會追蹤哪些項目？

如果點按事件發生在元素上，元素必須傳遞一些檢查以判斷AppMeasurement是否會將其視為連結。 所進行的檢查如下：

* 這是否為具有`href`屬性的`A`或`AREA`標籤？
* 是否有設定`s_objectID`變數的`onclick`屬性？
* 這是否為`INPUT`標籤或`SUBMIT`按鈕以及值或子文字？
* 這是否為`INPUT`標籤，且類型為`IMAGE`和`src`屬性？
* 這是否為`BUTTON`?

如果以上任一問題的答案為是，則會將該元素視為連結，並進行追蹤。

>[!IMPORTANT]
>
>AppMeasurement不會將具有屬性type=&quot;button&quot;的按鈕標籤視為連結。 請考慮移除按鈕標籤上的type=&quot;button&quot;，改為新增role=&quot;button&quot;或submit=&quot;button&quot;。

>[!IMPORTANT]
>
>AppMeasurement會將以「#」開頭之「href」的錨點標籤視為內部目標位置，而非連結（因為您並未離開頁面）。 依預設，Activity Map 不會追蹤這些內部目標位置。它只會追蹤將使用者導覽至新頁面的連結。

## Activity Map如何追蹤其他視覺化HTML元素？

a.透過`s.tl()`函式。

如果點按是透過`s.tl()`叫用發生，則Activity Map也會收到此點按事件，並判斷是否找到`linkName`字串變數。 在`s.tl()`執行期間，該linkName將設為Activity Map連結ID。 產生`s.tl()`呼叫的點按元素將用於判斷地區。 範例：

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b.透過`s_objectID`變數。 範例：

    &quot;&#39;將
    
    &lt;a>&lt;img>&lt;/a>
    
    &lt;a>文字連結到這&lt;/a>里
    
    
    &quot;&#39;

>[!IMPORTANT]
>
>在Activity Map中使用`s_objectID`時，必須在結尾加上分號(;)。

## 能提供一些會被追蹤的連結範例嗎？

### 範例 1

```
  <a hef="/home?lang=en>Home</a>
```

### 範例 2

```
 <input type="submit" value="Submit"/>
```

### 範例 3

```
  <input type="image" src="submit-button.png"/>
```

### 範例4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### 範例5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## 可以提供一些「不會」被追蹤的連結範例嗎？

1. 原因：錨記沒有有效的 `href`:
   `<a name="innerAnchor">Section header</a>`

1. 原因：`s_ObjectID`和`s.tl()`均不存在：

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. 原因：`s_ObjectID`和`s.tl()`均不存在：

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. 原因：&quot;src&quot;屬性缺少表單輸入元素：

   `<input type="image"/>`
