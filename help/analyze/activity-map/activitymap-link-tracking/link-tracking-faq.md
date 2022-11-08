---
description: 關於 Activity Map 中連結追蹤的常問問題。
title: 連結追蹤常見問題集
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: ht
source-wordcount: '516'
ht-degree: 100%

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

當使用者點選頁面時，就會進行 Activity Map 連結和區域識別。

## 預設會追蹤哪些項目？

如果點選事件發生在元素上，該元素必須傳遞一些檢查以判斷 AppMeasurement 是否將其視為連結。所進行的檢查如下:

* 這是否為具有 `href` 屬性的 `A` 或 `AREA` 標記？
* 是否有 `onclick` 屬性且設定 `s_objectID` 變數？
* 這是否為 `INPUT` 標記或具有值或子文字的 `SUBMIT` 按鈕？
* 這是否為具有類型 `IMAGE` 和 `src` 屬性的 `INPUT` 標記？
* 這是否為 `BUTTON`？

如果以上任一問題的答案為「是」，則會將該元素視為連結，並進行追蹤。

>[!IMPORTANT]
>
>AppMeasurement 不會將具有屬性 type=&quot;button&quot; 的按鈕標記視為連結。請考慮移除按鈕標記上的 type=&quot;button&quot;，改為新增 role=&quot;button&quot; 或 submit=&quot;button&quot;。

>[!IMPORTANT]
>
>AppMeasurement 會將包含以「#」開頭的「href」的錨點標記視為內部目標位置，而非連結 (因為您並沒有離開頁面)。 依預設，Activity Map 不會追蹤這些內部目標位置。它只會追蹤將使用者導覽至新頁面的連結。

## Activity Map 如何追蹤其他視覺化 HTML 元素？

a. 透過 `s.tl()` 功能。

如果透過 `s.tl()` 引動而發生點選，則 Activity Map 也將收到此點選事件並判斷是否找到 `linkName` 字串變數。在 `s.tl()` 執行期間，該 linkName 將設為 Activity Map 連結 ID。 引起 `s.tl()` 呼叫的已點選元素將用於判斷區域。範例:

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. 透過 `s_objectID` 變數。範例:

    ``` 
    
    &lt;img onclick=&quot;s_objectID=&#39;abc&#39;;&quot; src=&quot;someimageurl.png&quot;/>
    &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&#39;abc&#39;;&quot; >
    此處為連結文字
    &lt;/a>
    
    ```

>[!IMPORTANT]
>
>在 Activity Map 中使用 `s_objectID` 時，需要在結尾加上分號 (;)。

## 您可以提供一些會被追蹤的連結範例嗎？

### 範例 1

```
  <a hef="/home>Home</a>
```

### 範例 2

```
 <input type="submit" value="Submit"/>
```

### 範例 3

```
  <input type="image" src="submit-button.png"/>
```

### 範例 4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### 範例 5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## 您可以提供一些「不會」被追蹤的連結範例嗎？

1. 原因: 錨點標記沒有有效的 `href`:
   `<a name="innerAnchor">Section header</a>`

1. 原因: 不存在 `s_ObjectID` 或 `s.tl()`:

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. 原因: 不存在 `s_ObjectID` 或 `s.tl()`:

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. 原因:「src」屬性遺漏表單輸入元素:

   `<input type="image"/>`

