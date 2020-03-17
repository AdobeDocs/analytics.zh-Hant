---
description: 該量度指的是瀏覽器視窗內資料的水平/垂直距離。如需更具體資訊，請參閱瀏覽器
title: 瀏覽器寬度/高度
topic: Metrics
uuid: 1c0d3ea9-e001-4152-9bfc-8fe6406bc755
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# 瀏覽器寬度/高度

該量度指的是瀏覽器視窗內資料的水平/垂直距離。如需更具體資訊，請參閱瀏覽器

Adobe Analytics 僅會使用瀏覽時首次點擊的瀏覽器高度和寬度。其餘點擊不會取得同樣的瀏覽屬性。瀏覽器寬度/高度維度會在比較時擷取類似但相異的值[行動螢幕大小](/help/components/c-variables/dimensionslist/reports-mobile.md#topic_D306EA4558194488AC47A45B9C570150)。

例如，當您依行動裝置解析度劃分瀏覽器寬度或高度時，必須注意以下差異：

* 行動裝置解析度是指與裝置相關聯的實際值。例如，在「行動裝置解析度」下方，Galaxy S8 會顯示 2,960 x 1,440。裝置識別後，會從第三方服務擷取行動裝置解析度。
* 相較之下，在「瀏覽器高度和寬度」值下方，您會看見 740 x 360 的 CSS (邏輯) 值。瀏覽器值取決於 Javascript/CSS 資料。
* 如需簡短討論內容，請參閱[此討論串](https://stackoverflow.com/questions/8785643/what-exactly-is-device-pixel-ratio)。

