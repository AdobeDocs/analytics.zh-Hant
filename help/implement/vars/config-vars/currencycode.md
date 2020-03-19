---
title: currencyCode
desciption: For eCommerce sites, set the currency the page deals in.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# currencyCode

對於使用商務的網站，收入和貨幣是Analytics的重要組成部分。 許多網站，尤其是橫跨多個國家的網站，都使用不同的貨幣。 使用變 `currencyCode` 數可確保收入屬性為正確的貨幣。

如果 `currencyCode` 未定義，定義變數和貨幣事 [`products`](../page-vars/products.md) 件的貨幣值會被視為與報表套裝的貨幣相同。 請參 [閱「管理員使用指南](/help/admin/admin/general-acct-settings-admin.md) 」中的「一般帳戶設定」，以查看報表套裝的貨幣。

如果 `currencyCode` 已定義並符合報表套裝的貨幣，則不會套用貨幣轉換。

如 `currencyCode` 果已定義且與報表套裝的貨幣不同，Adobe會根據當天的匯率套用貨幣兌換。 Adobe與 [XE合作](https://xe.com) ，每天兌換貨幣。 所有儲存在資料收集伺服器中的值，最終都會儲存在報表套裝的貨幣中。

> [!IMPORTANT] 如果 `currencyCode` 包含無效值，則會捨棄整個點擊，造成資料遺失。 若您在實作中使用此變數，請確定此變數已正確定義。

此變數不會在點擊之間持續存在。 請確定此變數已定義於每個涉及收入或貨幣事件的頁面上。

## Adobe Experience Platform Launch中的貨幣代碼

貨幣代碼是設定Adobe Analytics擴充功 [!UICONTROL General] 能時accordion下的欄位。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. 按一下所要的屬性。
3. 前往標籤 [!UICONTROL Extensions] ，然後按一下「Adobe Analytics [!UICONTROL Configure] 」下的按鈕。
4. 展開accordion [!UICONTROL General] ，以顯示欄 [!UICONTROL Currency Code] 位。

您可以使用預設貨幣代碼或自訂貨幣代碼。 如果使用自訂貨幣代碼，請確定代碼有效。

## AppMeasurement和Launch自訂代碼編輯器中的s.currencyCode

變 `s.currencyCode` 數是字串，包含代表頁面貨幣的3個字母大寫代碼。

```js
s.currencyCode = "USD";
```

下列貨幣代碼有效：

| 貨幣代碼 | 貨幣說明 |
| --- | --- |
| `AED` | 阿拉伯聯合大公國迪拉姆 |
| `AFA` | 阿富汗尼 |
| `ALL` | 阿爾巴尼亞列克 |
| `AMD` | 亞美尼亞德拉姆 |
| `ANG` | 荷屬盾 |
| `AOA` | 安哥拉寬扎 |
| `ARS` | 阿根廷比索 |
| `AUD` | 澳大利亞元 |
| `AWG` | 阿魯巴盾 |
| `AZM` | 阿塞拜疆馬納特 |
| `BAM` | 波斯尼亞和黑塞格維那可兌換馬克 |
| `BBD` | 巴巴多斯元 |
| `BDT` | 孟加拉塔卡 |
| `BGN` | 保加利亞列弗 |
| `BHD` | 巴林第納爾 |
| `BIF` | 布隆迪法郎 |
| `BMD` | 百慕達元 |
| `BND` | 汶萊元 |
| `BOB` | 玻利維亞諾 |
| `BRL` | 巴西巴幣 |
| `BSD` | 巴哈馬元 |
| `BTN` | 不丹努紮姆 |
| `BWP` | 博茨瓦納普拉 |
| `BYR` | 白俄羅斯盧布 |
| `BZD` | 伯利茲元 |
| `CAD` | 加拿大元 |
| `CDF` | 剛果／金夏沙法郎 |
| `CHF` | 瑞士法郎 |
| `CLP` | 智利比索 |
| `CNY` | 中國人民幣 |
| `COP` | 哥倫比亞比索 |
| `CRC` | 哥斯大黎加科朗 |
| `CSD` | 塞爾維亞第納爾 |
| `CUP` | 古巴比索 |
| `CVE` | 佛得角埃斯庫多 |
| `CYP` | 賽普勒斯鎊 |
| `CZK` | 捷克共和國克朗 |
| `DJF` | 吉布提法郎 |
| `DKK` | 丹麥克朗 |
| `DOP` | 多明尼加共和國比索 |
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
| `GHC` | 加納塞地 |
| `GIP` | 直布羅陀鎊 |
| `GMD` | 岡比亞達拉西 |
| `GNF` | 幾內亞法郎 |
| `GTQ` | 瓜地馬拉格查爾 |
| `GYD` | 圭亞那元 |
| `HKD` | 港元 |
| `HNL` | 洪都拉斯倫皮拉 |
| `HRK` | 克羅地亞昆拉 |
| `HTG` | 海地古德 |
| `HUF` | 匈牙利福林 |
| `IDR` | 印尼盾 |
| `ILS` | 以色列新謝克爾 |
| `IMP` | 曼島鎊 |
| `INR` | 印度盧比 |
| `IQD` | 伊拉克第納爾 |
| `IRR` | 伊朗裏亞爾 |
| `ISK` | 冰島克朗 |
| `JEP` | 澤西鎊 |
| `JMD` | 牙買加元 |
| `JOD` | 約旦第納爾 |
| `JPY` | 日元 |
| `KES` | 肯尼亞先令 |
| `KGS` | 吉爾吉斯斯坦索姆 |
| `KHR` | 柬埔寨瑞爾 |
| `KMF` | 科摩羅法郎 |
| `KPW` | 北朝鮮元 |
| `KRW` | 韓元 |
| `KWD` | 科威特第納爾 |
| `KYD` | 開曼元 |
| `KZT` | 哈薩克坦吉 |
| `LAK` | 老撾基普 |
| `LBP` | 黎巴嫩鎊 |
| `LKR` | 斯里蘭卡盧比 |
| `LRD` | 利比里亞元 |
| `LSL` | 萊索托洛蒂 |
| `LTL` | 立陶宛立塔 |
| `LVL` | 拉脫維亞拉茲 |
| `LYD` | 利比亞第納爾 |
| `MAD` | 摩洛哥迪拉姆 |
| `MDL` | 莫爾達瓦列伊 |
| `MGA` | 馬達加斯加阿里亞里 |
| `MKD` | 馬其頓代納爾 |
| `MMK` | 緬幣 |
| `MNT` | 蒙古圖格裏克 |
| `MOP` | 澳門元 |
| `MRO` | 茅利塔尼亞烏吉亞 |
| `MTL` | 馬耳他里拉 |
| `MUR` | 毛里求斯盧比 |
| `MVR` | 馬爾代夫盧非亞 |
| `MWK` | 馬拉維克瓦查 |
| `MXN` | 墨西哥比索 |
| `MYR` | 馬來西亞林吉特 |
| `MZM` | 莫三比克梅蒂卡爾 |
| `NAD` | 納米比亞元 |
| `NGN` | 尼日利亞奈拉 |
| `NIO` | 尼加拉瓜金科多巴 |
| `NOK` | 挪威克朗 |
| `NPR` | 尼泊爾盧比 |
| `NZD` | 新西蘭元 |
| `OMR` | 阿曼裏亞爾 |
| `PAB` | 巴拿馬巴波亞 |
| `PEN` | 祕魯新托爾 |
| `PGK` | 巴布亞新幾內亞基納 |
| `PHP` | 菲律賓比索 |
| `PKR` | 巴基斯坦盧比 |
| `PLN` | 波蘭茲羅提 |
| `PYG` | 巴拉圭瓜拉尼 |
| `QAR` | 卡塔爾裏亞爾 |
| `ROL` | 羅馬尼亞列伊 |
| `RUR` | 俄羅斯盧布 |
| `RWF` | 盧旺達法郎 |
| `SAR` | 沙特裏亞爾 |
| `SBD` | 所羅門元 |
| `SCR` | 塞舌耳盧比 |
| `SDD` | 蘇丹第納爾 |
| `SEK` | 瑞典克朗 |
| `SGD` | 新加坡元 |
| `SHP` | 聖赫勒拿鎊 |
| `SIT` | 斯洛維尼亞托勒 |
| `SKK` | 斯洛伐克克朗 |
| `SLL` | 塞拉里昂利昂 |
| `SOS` | 索馬里先令 |
| `SPL` | 塞波加大公國幣 |
| `SRD` | 蘇里南元 |
| `SRG` | 蘇里南基爾德 |
| `STD` | 聖多美和普林西比多布拉 |
| `SVC` | 薩爾瓦多科朗 |
| `SYP` | 敘利亞鎊 |
| `SZL` | 斯威士蘭埃馬蘭吉尼 |
| `THB` | 泰銖 |
| `TJS` | 塔吉克斯坦索莫尼 |
| `TMM` | 土庫曼馬納特 |
| `TND` | 突尼斯第納爾 |
| `TOP` | 湯加邦加 |
| `TRL` | 土耳其里拉 |
| `TTD` | 特里尼達和多巴哥元 |
| `TVD` | 圖瓦盧元 |
| `TWD` | 新臺幣 |
| `TZS` | 坦桑尼亞先令 |
| `UAH` | 烏克蘭格裏夫納 |
| `UGX` | 烏干達先令 |
| `USD` | 美元 |
| `UYU` | 烏拉圭比索 |
| `UZS` | 烏茲別克斯坦索姆 |
| `VEB` | 委內瑞拉博利瓦 |
| `VND` | 越南盾 |
| `VUV` | 瓦努阿圖瓦圖 |
| `WST` | 薩摩亞塔拉 |
| `XAF` | Communauté Financière Africaine Francs B |
| `XAG` | 銀盎司 |
| `XAU` | 黃金盎司 |
| `XCD` | 東加勒比元 |
| `XDR` | 國際貨幣基金會特別提款權 |
| `XOF` | Communauté Financière Africaine Francs B |
| `XPD` | 鈀盎司 |
| `XPF` | Comptoirs Français du Pacifique Francs |
| `XPT` | 鉑盎司 |
| `YER` | 葉門裏亞爾 |
| `ZAR` | 南非蘭特 |
| `ZMK` | 尚比亞克瓦查 |
| `ZWD` | 辛巴威元 |
