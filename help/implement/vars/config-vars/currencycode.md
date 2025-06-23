---
title: 什麼是 currencyCode 變數以及該如何使用它？
description: 針對電子商務網站，設定頁面交易所使用的貨幣。
feature: Appmeasurement Implementation
exl-id: 3332c366-c472-4778-96c8-ef0aa756cca8
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '946'
ht-degree: 98%

---

# currencyCode

對使用商務功能的網站而言，收入和貨幣是 Analytics 的重要一環。許多網站使用不同的貨幣，尤其是橫跨多國的網站。使用 `currencyCode` 變數可確保將收入歸因於正確的貨幣。

貨幣轉換在每次點擊時使用以下邏輯。這些步驟適用於設定 [`products`](../page-vars/products.md) 變數的收入值，以及在報表套裝設定底下的[成功事件](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/conversion-var-admin/c-success-events/success-event.md) 中列為「貨幣」的所有事件。

* 如果 `currencyCode` 未定義，Adobe 假設所有貨幣值是報表套裝的貨幣。請參閱報表套裝設定中的[一般帳戶設定](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)，查看報表套裝的貨幣。
* 如果已定義 `currencyCode` 且與報表套裝的貨幣相同，則不會套用貨幣轉換。
* 如果已定義 `currencyCode` 且與報表套裝的貨幣不同，Adobe 會根據當天的匯率套用貨幣轉換。Adobe 的每日轉換貨幣業務與 [XE](https://xe.com) 合作。所有儲存在報表套裝中的值，都是採用報表套裝的貨幣。
* 如果 `currencyCode` 設為無效值，**則會捨棄整個點擊，造成資料遺失。**&#x200B;確保在使用時正確定義此變數。

此變數不會在點擊之間持續存在。請確定已在每個涉及收入或貨幣事件 (與報表套裝的預設貨幣不相符) 的頁面上定義此變數。

>[!NOTE]
>
>雖然不同頁面上可以有不同的貨幣代碼，但是單一點擊的所有貨幣量度都必須使用相同的貨幣。

實作此變數時，所有貨幣&#x200B;**必須**&#x200B;以句號做為貨幣分隔符號。例如，通常顯示逗號分隔符號的瑞典克朗必須修改為在 `products` 變數和所有貨幣事件中使用句號。Adobe 在報告中顯示正確的貨幣分隔符號。

## 使用 Web SDK 的貨幣代碼

貨幣代碼會對應至下列變數：

* [XDM物件](/help/implement/aep-edge/xdm-var-mapping.md)： `xdm.commerce.order.currencyCode`
* [資料物件](/help/implement/aep-edge/data-var-mapping.md)： `data.__adobe.analytics.currencyCode`或`data.__adobe.analytics.cc`

## 使用 Adobe Analytics 擴充功能的貨幣代碼

「貨幣代碼」是在設定 Adobe Analytics 擴充功能時，位於「[!UICONTROL 一般]」摺疊式功能表底下的欄位。

1. 使用您的 AdobeID 認證登入 [Adobe Experience Platform 資料彙集](https://experience.adobe.com/data-collection)。
1. 按一下所需的標籤屬性。
1. 前往「[!UICONTROL 擴充功能]」索引標籤，然後按一下 Adobe Analytics 底下的&#x200B;**[!UICONTROL 「設定」]**&#x200B;按鈕。
1. 展開[!UICONTROL 一般]摺疊式功能表，便會顯示[!UICONTROL 貨幣代碼]欄位。

您可以使用預設貨幣代碼或自訂貨幣代碼。如果使用自訂貨幣代碼，請確認代碼有效。

## Adobe Experience Platform Mobile SDK 中的貨幣代碼

貨幣代碼會透過 Adobe Analytics 擴充功能中的內容資料變數傳遞至 Adobe Experience Platform Mobile SDK。

1. 在 `trackState` 或 `trackAction` 期間，在內容資料變數中設定貨幣代碼。
1. 在 Adobe Analytics 管理工具中建立報表套裝的處理規則。 設定覆寫貨幣代碼變數的規則。
1. 在呼叫 `trackState` 或 `trackAction` 時，將貨幣代碼傳遞至 `products` 變數。

您可以使用預設貨幣代碼或自訂貨幣代碼。如果使用自訂貨幣代碼，請確認代碼有效。

## AppMeasurement 和 Analytics 擴充功能自訂程式碼編輯器中的 s.currencyCode

`s.currencyCode` 變數為字串，包含代表頁面上貨幣的 3 個大寫字母代碼。值區分大小寫。

```js
s.currencyCode = "USD";
```

下列貨幣代碼有效：

| 貨幣代碼 | 標籤 |
| --- | --- |
| `AED` | 阿拉伯聯合大公國迪拉姆 |
| `AFA` | 阿富汗尼 |
| `ALL` | 阿爾巴尼亞列克 |
| `AMD` | 亞美尼亞德拉姆 |
| `ANG` | 荷蘭盾 |
| `AOA` | 安哥拉匡撒 |
| `ARS` | 阿根廷披索 |
| `AUD` | 澳大利亞元 |
| `AWG` | 阿魯巴盾 |
| `AZM` | 亞塞拜然新馬納特 |
| `BAM` | 波士尼亞與赫塞哥維納波赫馬克 |
| `BBD` | 巴貝多元 |
| `BDT` | 孟加拉塔卡 |
| `BGN` | 保加利亞列弗 |
| `BHD` | 巴林迪納 |
| `BIF` | 蒲隆地法郎 |
| `BMD` | 百慕達元 |
| `BND` | 汶萊元 |
| `BOB` | 玻利維亞諾 |
| `BRL` | 巴西黑奧 |
| `BSD` | 巴哈馬元 |
| `BTN` | 不丹那特倫 |
| `BWP` | 波札那納普拉 |
| `BYR` | 白俄羅斯盧布 |
| `BZD` | 貝里斯元 |
| `CAD` | 加拿大元 |
| `CDF` | 剛果/金夏沙法郎 |
| `CHF` | 瑞士法郎 |
| `CLP` | 智利披索 |
| `CNY` | 中國人民幣 |
| `COP` | 哥倫比亞披索 |
| `CRC` | 哥斯大黎加科隆 |
| `CSD` | 塞爾維亞戴納 |
| `CUP` | 古巴披索 |
| `CVE` | 維德角埃斯庫多 |
| `CYP` | 賽浦路斯鎊 |
| `CZK` | 捷克共和國克朗 |
| `DJF` | 吉布提法郎 |
| `DKK` | 丹麥克朗 |
| `DOP` | 多明尼加共和國披索 |
| `DZD` | 阿爾及利亞第納爾 |
| `EEK` | 愛沙尼亞克朗 |
| `EGP` | 埃及鎊 |
| `ERN` | 厄立特里亞納克法 |
| `ETB` | 衣索比亞比爾 |
| `EUR` | 歐元 |
| `FJD` | 斐濟元 |
| `FKP` | 福克蘭鎊 |
| `GBP` | 英鎊 |
| `GEL` | 喬治亞拉里 |
| `GGP` | 根西島鎊 |
| `GHC` | 加納席迪 |
| `GIP` | 直布羅陀鎊 |
| `GMD` | 甘比亞達拉西 |
| `GNF` | 幾內亞法郎 |
| `GTQ` | 瓜地馬拉格查爾 |
| `GYD` | 圭亞那元 |
| `HKD` | 港元 |
| `HNL` | 洪都拉斯雷匹拉 |
| `HRK` | 克羅埃西亞庫納 |
| `HTG` | 海地古德 |
| `HUF` | 匈牙利福林 |
| `IDR` | 印尼盾 |
| `ILS` | 以色列新謝克爾 |
| `IMP` | 曼島鎊 |
| `INR` | 印度盧比 |
| `IQD` | 伊拉克第納爾 |
| `IRR` | 伊朗里亞爾 |
| `ISK` | 冰島克朗 |
| `JEP` | 澤西鎊 |
| `JMD` | 牙買加元 |
| `JOD` | 約旦第納爾 |
| `JPY` | 日元 |
| `KES` | 肯尼亞先令 |
| `KGS` | 吉爾吉斯索姆 |
| `KHR` | 柬埔寨瑞爾 |
| `KMF` | 科摩羅法郎 |
| `KPW` | 北朝鮮元 |
| `KRW` | 韓元 |
| `KWD` | 科威特第納爾 |
| `KYD` | 開曼元 |
| `KZT` | 哈薩克坦吉 |
| `LAK` | 寮國基普 |
| `LBP` | 黎巴嫩鎊 |
| `LKR` | 斯里蘭卡盧比 |
| `LRD` | 賴比瑞亞元 |
| `LSL` | 賴索托洛蒂 |
| `LTL` | 立陶宛立塔 |
| `LVL` | 拉脫維亞拉茲 |
| `LYD` | 利比亞第納爾 |
| `MAD` | 摩洛哥迪拉姆 |
| `MDL` | 摩爾多瓦雷 |
| `MGA` | 馬達加斯加阿里亞里 |
| `MKD` | 馬其頓代納爾 |
| `MMK` | 緬甸元 |
| `MNT` | 蒙古圖格里克 |
| `MOP` | 澳門元 |
| `MRO` | 茅利塔尼亞烏吉亞 |
| `MTL` | 馬耳他里拉 |
| `MUR` | 模里西斯盧比 |
| `MVR` | 馬爾地夫盧非亞 |
| `MWK` | 馬拉維克瓦查 |
| `MXN` | 墨西哥披索 |
| `MYR` | 馬來西亞林吉特 |
| `MZM` | 莫三比克梅蒂卡爾 |
| `NAD` | 納米比亞元 |
| `NGN` | 尼日利亞奈拉 |
| `NIO` | 尼加拉瓜金科多巴幣 |
| `NOK` | 挪威克朗 |
| `NPR` | 尼泊爾盧比 |
| `NZD` | 紐西西蘭元 |
| `OMR` | 阿曼里亞爾 |
| `PAB` | 巴拿馬巴波亞 |
| `PEN` | 祕魯新托爾 |
| `PGK` | 巴布亞新幾內亞基納 |
| `PHP` | 菲律賓披索 |
| `PKR` | 巴基斯坦盧比 |
| `PLN` | 波蘭茲羅提 |
| `PYG` | 巴拉圭瓜拉尼 |
| `QAR` | 卡達里亞爾 |
| `ROL` | 羅馬尼亞列伊 |
| `RUR` | 俄羅斯盧布 |
| `RWF` | 盧安達法郎 |
| `SAR` | 沙烏地阿拉伯里亞爾 |
| `SBD` | 所羅門元 |
| `SCR` | 塞席爾盧比 |
| `SDD` | 蘇丹第納爾 |
| `SEK` | 瑞典克朗 |
| `SGD` | 新加坡元 |
| `SHP` | 聖赫勒拿鎊 |
| `SIT` | 斯洛維尼亞托勒 |
| `SKK` | 斯洛伐克克朗 |
| `SLL` | 獅子山利昂 |
| `SOS` | 索馬利亞先令 |
| `SPL` | 塞波加大公國幣 |
| `SRD` | 蘇利南元 |
| `SRG` | 蘇利南基爾德 |
| `STD` | 聖多美普林西比杜布拉 |
| `SVC` | 薩爾瓦多科朗 |
| `SYP` | 敘利亞鎊 |
| `SZL` | 史瓦濟蘭史鍰 |
| `THB` | 泰銖 |
| `TJS` | 塔吉克索莫尼 |
| `TMM` | 土庫曼馬納特 |
| `TND` | 突尼西亞第納爾 |
| `TOP` | 東加邦加 |
| `TRL` | 土耳其里拉 |
| `TTD` | 千里達幣 |
| `TVD` | 吐瓦魯元 |
| `TWD` | 新台幣 |
| `TZS` | 坦尚尼亞先令 |
| `UAH` | 烏克蘭荷林夫納 |
| `UGX` | 烏干達先令 |
| `USD` | 美元 |
| `UYU` | 烏拉圭披索 |
| `UZS` | 烏茲別克索姆 |
| `VEB` | 委內瑞拉玻利瓦 |
| `VND` | 越南盾 |
| `VUV` | 萬那杜那杜幣 |
| `WST` | 薩摩亞塔拉 |
| `XAF` | 中非法郎 |
| `XAG` | 銀盎司 |
| `XAU` | 黃金盎司 |
| `XCD` | 東加勒比元 |
| `XDR` | 國際貨幣基金會特別提款權 |
| `XOF` | 中非法郎 |
| `XPD` | 鈀盎司 |
| `XPF` | 太平洋法蘭西共同體法郎 |
| `XPT` | 鉑盎司 |
| `YER` | 葉門里亞爾 |
| `ZAR` | 南非鍰 |
| `ZMK` | 尚比亞夸加 |
| `ZWD` | 辛巴威元 |
