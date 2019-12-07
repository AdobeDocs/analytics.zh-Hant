---
description: 將值輸入變數中時，有幾個最佳實務準則可供依循。
keywords: Analytics Implementation
subtopic: Troubleshooting
title: 使用引號
topic: Developer and implementation
uuid: 9f09c48b-7ae5-441e-8635-fd6bdc2e94c7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 使用引號

將值輸入變數中時，有幾個最佳實務準則可供依循。

您可以使用單引號或雙引號，但請確保一致性。若您使用單引號，請一律使用單引號。若您使用雙引號，請一律使用雙引號。以下提供兩個正確範例。

```js
s.prop2='test' (single quotes)
```

```js
s.prop2="test" (double quotes)
```

請確定您已關閉智慧引號。若您使用單引號，而您的變數值中含有縮寫符號，JavaScript 會將縮寫符號解譯為單引號。這表示那裡是字串結尾。考量下列範例:

```js
s.pageName='John's Home Page'
```

在此案例中，JavaScript 會將 "John's" 中的縮寫符號 (也是單引號) 解譯為字串結尾。由於 ''s Home Page" 在 JavaScript 中沒有意義，因此會導致錯誤，使影像要求無法執行。下列兩個範例都是可行的: 

```js
s.pageName='John\'s Home Page'
```

```js
s.pageName="John's Home Page"
```

在第一個範例中，您可以在縮寫符號前面插入反斜線 (\)，以逸出縮寫符號。這會對 JavaScript 指出縮寫符號並非字串結尾，而是字串的一部分。字串隨後如預期在右單引號處結尾。第二個範例在整個字串的兩側使用雙引號。在此案例中，單引號無法指出字串結尾。若字串中包含雙引號，也是如此。s.pageName="Team Says "We Win!"" 一值是不正確的，因為字串中使用了雙引號，且字串兩側也使用雙引號。若輸入為 s.pageName="Team Says \"We Win! \""，就會是正確的。
