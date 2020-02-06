---
description: 說明如何定義多貨幣支援的目標貨幣代碼。
title: 多貨幣支援
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 63a6ca92ae5fe103648c74bd16bcdf90858c71f3

---


# 多貨幣支援

本檔案說明如何定義多貨幣支援的目標貨幣代碼。

目標貨幣代碼定義在三個層級：

## 頁面層級

您可以在頁面層級設定目標貨幣的JavaScript變數。 網站擁有者會以適當的三字母ISO 4217貨幣代碼（如本檔案下方所列）來設定此變數。 若未 [在此層級設定currencyCode](https://docs.adobe.com/content/help/en/analytics/implementation/vars/config-vars/currencycode.html) 變數，預設貨幣將與報表套裝中指定的貨幣相同。 如果頁面層級的變數與報表套裝中指定的變數衝突，報表套裝中的變數將優先。


## 報表套裝層級

建立 **報表套裝時** ，會指 [定基本貨幣](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/new-report-suite/new-report-suite.html)。 這是貨幣的預設設定，優先於頁面層級所設定的貨幣代碼。 因此，如果報表套裝的訂單接受美元、歐元和英鎊，而報表套裝的預設貨幣代碼設定為「美元」，則報表後端資料庫會將所有交易轉換為美元。

行銷報告會使用影像要求發生時的兌換率，將頁面層級貨幣值轉換為預設報表套裝貨幣值。 報表套裝使用「美元」作為預設貨幣。


## 報表層級

使用者可以設定使用者登入作業的預設報告貨幣。 這可透過任何「**轉換報表**」中的「顯示選項」連結進行存取。行銷報表使用報表執行時的匯率，將報表套裝貨幣值轉換為報表指定的貨幣值。

## 支援的貨幣代碼(ISO 4217)

Analytics目前支援下列貨幣格式進行轉換交易：


阿富汗阿富汗尼(AFA)

阿富汗阿富汗尼(AFN)

阿爾巴尼亞列克(ALL)

&#39;DZD&#39;阿爾及利亞第納爾(DZD)

安哥拉寬扎(AOA)

&#39;ARS&#39;阿根廷比索(ARS)

&#39;AMD&#39;亞美尼亞德拉姆(AMD)

阿魯巴盾(AWG)

澳元(AUD)

阿塞拜強馬納特(AZM)

阿塞拜強新馬納特(AZN)

&#39;BSD&#39;巴哈馬元(BSD)

&#39;BHD&#39;巴林第納爾(BHD)

&#39;BDT&#39;孟加拉塔卡(BDT)

巴貝多元

白俄羅斯盧布

貝里斯元

百慕達元

《努爾特魯姆》不丹努特魯姆(BTN)

玻利維亞諾

&quot;BAM&quot;波——黑可轉換馬克(BAM)

波札那普拉斯(BWP)

巴西雷亞爾(BRL)

汶萊元(BND)

保加利亞列弗(BGN)

蒲隆地法郎(BIF)

柬埔寨瑞爾

加拿大元(CAD)

&#39;CVE&#39; Cape Verde Escudos(CVE)

開曼元

&#39;CLP&#39;智利比索(CLP)

人民幣中國元人民幣（元）

&quot;哥倫比亞警察&quot;比索

&quot;XOF&quot; Communauté Financière Africaine Francs BCEAO(XOF)

非洲法郎（中非）

葛摩法郎(KMF)

&quot;XPF&quot;太平洋法郎(XPF)

&quot;CDF&quot;剛果／金夏沙法郎(CDF)

哥斯大黎加科朗(CRC)

克羅埃西亞庫納(HRK)

古巴可兌換比索

&#39;CUP&#39;古巴比索(CUP)

賽普勒斯鎊(CYP)

捷克克朗

丹麥克朗(DKK)

吉布地法郎（吉布地法郎）

&#39;DOP&#39;多明尼加共和國比索(DOP)

東加勒比元

埃及鎊

SVC薩爾瓦多科朗(SVC)

厄恩厄里特利亞納克法(ERN)

&#39;XBT&#39; ERR(XBT)

《EEK》愛沙尼亞克羅尼(EEK)

衣索匹亞比爾(ETB)

歐元（歐元）

福克蘭鎊(FKP)

斐濟元

甘比亞達拉西(GMD)

&#39;GEL&#39; Georgia Lari(GEL)

迦納塞地

迦納塞地

直布羅陀鎊

XAU金盎司(XAU)

瓜地馬拉格查爾(GTQ)

根西島鎊

&#39;GNF&#39;幾內亞法郎(GNF)

蓋亞那元(GYD)

&#39;HTG&#39;海地古德(HTG)

宏都拉斯倫皮拉(HNL)

港元(HKD)

匈牙利福林(HUF)

冰島克朗(ISK)

印度盧比(INR)

「IDR」印度尼西亞盾(IDR)

XDR國際貨幣基金特別提款權(XDR)

&#39;IRR&#39;伊朗里亞爾(IRR)

伊拉克第納爾(IQD)

IMP曼島鎊(IMP)

「ILS」以色列新謝克爾(ILS)

牙買加元

JPY日圓(JPY)

JEP澤西鎊(JEP)

&#39;JOD&#39;約旦第納爾(JOD)

&#39;KZT&#39;哈薩克堅戈(KZT)

肯亞先令(KES)

&#39;KWD&#39;科威特第納爾(KWD)

&quot;KGS&quot;吉爾吉斯索姆(KGS)

寮國基普(LAK)

拉脫維亞拉蒂(LVL)

黎巴嫩鎊

賴索托馬洛蒂(LSL)

賴比瑞亞元

利比亞第納爾(LYD)

立陶宛立塔利泰(LTL)

澳門幣(MOP)

馬其頓代納爾(MKD)

馬達加斯加阿里亞里(MGA)

馬拉威克瓦查斯(MWK)

&#39;MYR&#39;馬來西亞林吉特(MYR)

&#39;MVR&#39;馬爾地夫盧菲亞(MVR)

&#39;MTL&#39;馬爾他里拉(MTL)

茅利塔尼亞烏吉亞(MRO)

模里西斯盧比(MUR)

「MXN」墨西哥比索(MXN)

摩爾多瓦列伊(MDL)

蒙古圖格里克（圖格里克）

&#39;MAD&#39;摩洛哥迪拉姆(MAD)

莫桑比克梅蒂卡爾(MZN)

莫桑比克梅蒂卡爾(MZM)

緬甸緬元

納米比亞元(NAD)

尼泊爾盧比

荷屬荷屬盾(ANG)

紐西蘭元(NZD)

尼加拉瓜科多巴(NIO)

奈及利亞奈拉(NGN)

朝鮮元(KPW)

挪威克朗(NOK)

阿曼里亞爾

巴基斯坦盧比(PKR)

XPD鈀盎司(XPD)

巴拿馬巴波亞(PAB)

巴布亞紐幾內亞基那(PGK)

巴拉圭瓜拉尼語(PYG)

&#39;PEN&#39;秘魯新托爾(PEN)

「PHP」菲律賓比索(PHP)

「XPT」鉑盎司(XPT)

波蘭茲羅提(PLN)

卡達里亞爾

羅爾羅馬尼亞列伊（羅爾）

羅恩羅馬尼亞新列伊(RON)

俄羅斯盧布

俄羅斯盧布

盧安達法郎(RWF)

聖赫勒拿鎊

&#39;WST&#39;薩摩亞塔拉(WST)

聖多美和普林西比多布拉(STD)

沙特里亞爾

SPL公國幣(SPL)

塞爾維亞第納爾

&#39;CSD&#39;塞爾維亞第納爾(CSD)

塞舌耳盧比(SCR)

獅子山利昂(SLL)

&quot;XAG&quot;銀盎司(XAG)

新加坡元

&#39;SKK&#39;斯洛伐克克朗(SKK)

斯洛維尼亞托勒(SIT)

索羅門群島元

&#39;SOS&#39;索馬利亞先令(SOS)

南非蘭特(ZAR)

韓國元(KRW)

斯里蘭卡盧比(LKR)

「SDD」蘇丹第納爾(SDD)

SDG蘇丹鎊

蘇利南元

蘇利南盾

史瓦濟蘭埃馬蘭吉尼(SZL)

瑞典克朗(SEK)

瑞士法郎(CHF)

敘利亞鎊

新台幣（新台幣）

塔吉克索莫尼(TJS)

坦尚尼亞先令(TZS)

泰銖(THB)

「頂級」東加邦加（頂級）

千里達和多巴哥元

&#39;TND&#39;突尼西亞第納爾(TND)

土耳其里拉

土耳其里拉

土庫曼馬納特

土庫曼新馬納特

吐瓦魯元(TVD)

&#39;UGX&#39;烏干達先令(UGX)

烏克蘭格里夫納(UAH)

阿聯酋迪拉姆(AED)

英鎊(GBP)

「USD」選定美元(USD)

烏拉圭比索(UYU)

烏茲別克索姆(UZS)

萬那杜瓦圖(VUV)

委內瑞拉玻利瓦爾

委內瑞拉博利瓦斯富爾特斯(VEF)

越南盾(VND)

葉門裡亞爾(YER)

尚比亞克瓦查(ZMK)

尚比亞克瓦查(ZMW)

《ZWD》辛巴威元(ZWD)


## AppMeasurement.js範例

變 `currencyCode` 數可在AppMeasurement.js檔案中全域定義。 在此檔案中定義currencyCode變數，可確保所有貨幣交易都使用統一的貨幣代碼。 下列範例將歐元指定 `currencyCode` 為AppMeasurement.js檔 `CONFIG SECTION` 案中的變數。 所有購買事件都會以報告為「歐元」交易來解讀。

```
/************************** CONFIG SECTION **************************/ 
/* You may add or alter any code config here. */ 
s.account="devnow"
s.currencyCode="EUR"
s.trackInlineStats=true 
s.linkLeaveQueryString=false 
s.linkTrackVars="None" 
s.linkTrackEvents="None" 
***
    
```

如需編輯AppMeasurement.js檔案的詳細資訊，請參 [閱將程式碼插入AppMeasurement.js檔案](https://docs.adobe.com/content/help/en/analytics/implementation/implement-analytics-with-dtm/analytics-tool/t-appmeasurement-code.html)。

## 其他實施注意事項

* 請記住，雖然貨幣代碼可以在頁面之間變更，但指定頁面請求上定義的所有轉換行項目都必須使用相同的貨幣（例如，您不能在相同的頁面檢視上定義歐元、英鎊和美元）。 如果您不想進行任何貨幣兌換，應將currencyCode值留空。 這會使傳送的值直接傳遞至無轉換的報表。

* 設定無效的currencyCode（任何不在「支援的貨幣代碼」清單中的值），會排除整個點擊，且不會收集該交易的資料。 在生產 `currencyCode` 中設定之前，請使用測試報表套裝來確認資料已收集且貨幣轉換正確。

* 不使用句點 (.) 作為分隔符號的貨幣，必須修改成使用句點來代替一般分隔符號。例如，使用逗號作為分隔符號的瑞典克朗，必須修改成使用句點來代替逗號。Analytics會使用逗號來分隔值，而且資料無法正確傳入。 該時段會將值正確傳遞至報表。
