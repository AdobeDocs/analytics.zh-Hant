---
description: 登入點代表指定的值在瀏覽中是被擷取的第一個值之次數。登入點在每次瀏覽時只能計入一次。但是，如果未定義變數，則不一定要是第一次點擊。
title: 登入點
topic: Metrics
uuid: c4608b66-b70c-4e98-b7c6-9be5fbe4ec9c
translation-type: tm+mt
source-git-commit: 8d6685d241443798be46c19d70d8150d222ab9e8

---


# 登入點

「登入點」代表指定值在瀏覽中被擷取為第一個值的次數。 登入點在每次瀏覽時只能計入一次。但是，如果未定義變數，則不一定要是第一次點擊。

自 2020 年 3 月起，Analysis Workspace 已變更「無」值與輸入/結束動作的互動方式。由於您現在可以在分析工作區中開啟或關閉「無」，因此我們會在進入或退出後套用「無」，而（對於evar）以前會套用它。  例如，假設瀏覽的第一次點擊沒有eVar21的值，但第二次點擊則有。 在「Reports &amp; Analytics」中，該輸入會顯示「未指定」，但在 Analysis Workspace 中，這會顯示第二次點擊的值。

登入頁面有瀏覽劃分範圍，代表它們持續存在於一次瀏覽的所有點擊間。有關詳細資訊，請參閱[劃分和分段容器](https://docs.adobe.com/content/help/en/analytics/components/segmentation/seg-overview.html)。
