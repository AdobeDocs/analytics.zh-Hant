---
description: 條件決定觸發事件型規則的時機。
keywords: Dynamic Tag Management;rule;create rule;new rule;event-based rule;delay link activation;apply event handler directly to element;bubbling;event bubbling
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: 建立事件型規則的條件
uuid: a847391c-5aec-4d64-8a35-388587731598
translation-type: ht
source-git-commit: ebf149df7974f9f2889b6fe938088eda90c84051

---


# 建立事件型規則的條件

條件決定觸發事件型規則的時機。

1. 選取您要追蹤的互動類型，例如滑鼠點按或表單提交。

   ![](assets/condition-event-based.png)

   如需詳細資訊，請參閱 Adobe 標籤管理產品文件中的[事件類型](https://marketing.adobe.com/resources/help/zh_TW/dtm/event_types.html)。

1. 視需要啟用下列選項：

   | 元素 | 說明 |
   |--- |--- |
   | 延遲連結啟動 | 如果事件會啟動連結，但您想要將連結延遲到事件有時間引發才啟動，請啟用此選項。 |
   | 將事件處理程式直接套用至元素 | 將事件處理程式套用至已鎖定作為目標的特定元素。此設定與瀏覽器中的事件反昇與分層概念相連結。 |

   例如，當您按一下錨點標籤內的影像時 (例如 `<a href="abc.html"><img src="xyz.png"/></a>`)，因為標籤位於反昇資料流中，您可能預期此點按會與該錨點標籤相關聯。不過，當您在開發人員工具中檢查此點按時，該點按可能實際只影響 `<img>` 標籤。若要確保事件受到正確處理，請將點按與 `<img>` 標籤建立關聯，而不依賴瀏覽器將點按向上反昇至父級元素。事件 (如點按) 可能會向上反昇至 `<body>`。請務必瞭解事件實際綁定到的位置，並明確鎖定此位置作為目標，以確保規則可正確引發。

   *事件反昇*&#x200B;意思是事件會先由最內層的元素擷取與處理，然後再傳播到外層元素。

1. 指定您要追蹤的標籤名稱，以及標籤中其他您要比對的屬性。

   ![](assets/condition-event-based2.png)

   如需尋找正確元素標籤的相關資訊，請參閱 Dynamic Tag Management 產品文件中的[使用 CSS 選取器](https://marketing.adobe.com/resources/help/zh_TW/dtm/css-selector.html)。

1. 選取並設定您想要綁定到規則的任何其他準則或條件類型。

   ![](assets/condition-event-based3.png)

1. 指定與事件反昇有關的偏好設定。

   事件反昇是 HTML DOM 中傳播事件的一種方式。

   | 若您... | 勾選此選項 |
   |--- |--- |
   | 希望所識別之規則選擇器之子項元素上的相關互動要引發規則。 | 允許子項元素上的事件反昇。 |
   | 希望在子項元素已自行觸發事件時防止事件反昇。 | 若子項元素已觸發事件，則不允許。 |
   | 不希望所識別之規則選取器的事件超越事件階層中的元素本身。 | 不允許事件向上反昇至父級。 |
