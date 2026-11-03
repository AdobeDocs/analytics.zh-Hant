---
title: 反向連結類型
description: 反向連結的類型，視訪客來自何處而定。
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
TQID: 'https://experienceleague.adobe.com/KPTS2iWls0V8I2gI0xcH1V89w0stZyVq6jWdQyEyrLY'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b7156124-d291-4de4-ac0c-ed17d8078449
    internal-label: AI Tools
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: b4c7365f660ff093731d55c7aba9cae5ade76789
workflow-type: tm+mt
source-wordcount: '871'
ht-degree: 47%
---
# 反向連結類型

「反向連結型別」[維度](overview.md)會報告訪客在點進哪些通用管道後到達您的網站。 Adobe 會維護每個維度項目的規則，不同於由您的組織維護各個管道之規則的[行銷管道](marketing-channel.md)。

## 將資料填入此維度中

Adobe從每個點選的[反向連結](referrer.md)衍生此維度，並將其與Adobe內部的多個查閱表格比對。 沒有可設定的變數。 因為每個值都相依於反向連結，請確定反向連結維度和[內部URL篩選器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)已正確設定。

| 屬性 | 價值 |
| --- | --- |
| **AppMeasurement變數** | 無（衍生自反向連結） |
| **網頁SDK / XDM欄位** | 無（衍生自反向連結） |
| **查詢引數** | 不適用 |
| **XML標籤** | 不適用 |
| **位元組限制** | 不適用 |
| **持續性** | 不適用 |

## 維度項目

維度項目包含點擊的反向連結類型。 特定值包括：

* **分類/建立書籤**：點擊沒有反向連結資料。 此值包含來自[對話式AI工具的造訪，這些工具會開啟沒有反向連結](#include-ai-traffic-that-has-no-referrer)的連結。
* **搜尋引擎**：反向連結來自於已認可、且包含關鍵字查詢字串的搜尋引擎。
* **交談AI工具**：反向連結來自於認可的交談AI工具。
* **社交網路：**：反向連結資料屬於 Adobe 認可的社交網路。
* **其他網站**：反向連結資料不屬於 Adobe 認可的搜尋引擎或社交網路。
* **無JavaScript**：反向連結來自於未啟用JavaScript的瀏覽器。
* **硬碟**：反向連結源自於訪客硬碟上的網頁本機複本。
* **電子郵件**：反向連結源自於具有通訊協定 `imap://` 或 `mail://` 的 URL。 其中不包括線上電子郵件服務，因為這些服務通常使用 `https://` 通訊協定。

### 對話式人工智慧工具

>[!IMPORTANT]
>
>此值僅包含具有下列清單中的反向連結的造訪。 有些交談AI工具（例如ChatGPT）在開啟連結時不會傳送反向連結，因此不會包含其造訪。 如需詳細資訊，請參閱[包含沒有反向連結的AI流量](#include-ai-traffic-that-has-no-referrer)。

下列清單列出Adobe所使用的「對話式AI工具」查詢表。 Adobe 提供此清單給 Adobe Analytics 客戶參考。 如果您想要建議 Adobe 在此清單中新增某個網域，請讓組織中的支援委派聯絡客戶服務。

* `https://chatgpt.com`
* `https://chat.com`
* `https://chat.deepseek.com`
* `https://chat.openai.com`
* `https://doubao.com`
* `https://duck.ai`
* `https://gemini.google.com`
* `https://copilot.microsoft.com`
* `https://m365.cloud.microsoft`
* `https://perplexity.ai`
* `https://labs.perplexity.ai`
* `https://playground.perplexity.ai`
* `https://claude.ai`
* `https://grok.com`
* `https://komo.ai`
* `https://phind.com`
* `https://poe.com`
* `https://blackbox.ai`
* `https://chat.mistral.ai`
* `https://meta.ai`
* `https://you.com`

#### 包括沒有反向連結的AI流量

有些對話式AI工具（包括ChatGPT）會開啟連結，而不會傳送反向連結。 Adobe會在「分類/建立書籤」底下報告這些造訪，而非「對話式AI工具」。 AI工具可隨時變更其開啟連結的方式。 如果「對話式AI工具」流量下降，工具可能會停止傳送反向連結。 下跌並不表示Adobe Analytics遺失資料。

有些工具會將UTM查詢字串引數新增至其開啟的連結，例如`utm_source=chatgpt.com`或`utm_source=perplexity`，而非反向連結。 若要從對話式AI工具取得更完整的流量計數，請搭配使用UTM引數與「對話式AI工具」值：

* **在變數中擷取UTM引數**：將eVar設定為登陸頁面URL的`utm_source`值。 使用[`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md)外掛程式、Web SDK或Adobe Analytics擴充功能中的URL引數功能，或讀取查詢字串引數的[處理規則](/help/admin/tools/manage-rs/edit-settings/general/processing-rules/pr-use-cases.md)。
* **為AI工具建立行銷管道**：建立符合任何條件的[行銷管道處理規則](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)。 新增AI工具使用的每個值（例如`chatgpt.com`或`perplexity`）的&#x200B;**[!UICONTROL Referrer Is Conversational AI]**&#x200B;條件和&#x200B;**[!UICONTROL 查詢字串引數]** `utm_source`條件。
* **建立區段**：建立符合「反向連結型別」等於「對話式AI工具」或您的UTM eVar包含AI工具所使用值的[區段](/help/components/segmentation/seg-overview.md)。 由於[頁面URL](page-url.md)維度包含查詢字串，因此您也可以比對頁面URL包含`utm_source=chatgpt.com`。 此選項不需變更實作即可運作。

有些AI工具不會傳送反向連結或UTM引數， 您無法將來自這些工具的流量識別為AI流量。

### 社交網路

下列清單列出 Adobe 所使用的「社交網路」查閱表格。 Adobe 提供此清單給 Adobe Analytics 客戶參考。 如果您想要建議 Adobe 在此清單中新增某個網域，請透過組織中的支援委派聯絡客戶服務。

>[!NOTE]
>
>此清單不同於[行銷管道處理規則](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md)中的社交網路預設清單。

* `12seconds.tv`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `answers.yahoo.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blog.seesaa.jp`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `bsky.app`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `delicious.com`
* `deviantart.com`
* `digg.com`
* `diigo.com`
* `disqus.com`
* `draugiem.lv`
* `facebook.com`
* `faceparty.com`
* `fc2.com`
* `flickr.com`
* `flixster.com`
* `fotolog.com`
* `foursquare.com`
* `friendfeed.com`
* `friendsreunited.com`
* `friendsreunited.co.uk`
* `friendster.com`
* `fubar.com`
* `gaiaonline.com`
* `geni.com`
* `go.bsky.app`
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `hi5.com`
* `hotnews.infoseek.co.jp`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `jp.myspace.com`
* `kaixin001.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `likeshop.me`
* `linkedin.com`
* `linkin.bio`
* `livejournal.com`
* `lnkd.in`
* `meetup.com`
* `me2day.net`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
* `mp.weixin.qq.com`
* `multiply.com`
* `mumsnet.com`
* `myheritage.com`
* `mylife.com`
* `myspace.com`
* `myyearbook.com`
* `nasza-klasa.pl`
* `matome.naver.jp`
* `netlog.com`
* `nettby.no`
* `netvibes.com`
* `nextdoor.com`
* `nicovideo.jp`
* `ning.com`
* `odnoklassniki.ru`
* `ok.ru`
* `orkut.com`
* `pakila.jp`
* `photobucket.com`
* `pinterest.com`
* `pinterest.co.uk`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `reddit.com`
* `renren.com`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `snapchat.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.163.com`
* `t.co`
* `t.hexun.com`
* `t.people.com.cn`
* `t.qq.com`
* `t.sina.com.cn`
* `t.sohu.com`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
* `threads.com`
* `threads.net`
* `tiktok.com`
* `toutiao.com`
* `tripit.com`
* `trombi.com`
* `trytrend.jp`
* `tuenti.com`
* `tumblr.com`
* `twine.com`
* `twitter.com`
* `uhuru.jp`
* `viadeo.com`
* `vimeo.com`
* `vk.com`
* `wayn.com`
* `web-cdn.bsky.app`
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `x.com`
* `xanga.com`
* `xing.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yozm.daum.net`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### 「其他網站」維度項目中的搜尋引擎

當您在「反向連結類型」維度中檢視特定網域時，可能會發現某些您原本預期應列在「搜尋引擎」下方的網域，實際上卻列在「其他網站」下方。 例如，您可能會在「其他網站」下方看到 `'google.com'`。

* **「搜尋引擎」維度項目中的搜尋引擎網域**：反向連結符合由 Adobe 分類為搜尋引擎的所有條件。 反向連結網域是有效的搜尋引擎， *且*&#x200B;反向連結 URL 包含關鍵字查詢字串參數。
* **「其他網站」維度項目中的搜尋引擎網域**：反向連結 URL 不符合分類為搜尋引擎的所有條件。 常見的範例包括搜尋以外的其他功能專用的子網域。 例如，`mail.google.com` 或 `autos.yahoo.com` 不是搜尋引擎，但位於通常與搜尋相關聯的上層網域上。 這些子網域不包含關鍵字查詢字串，正因如此，這些子網域才會包含在「其他網站」下，而非「搜尋引擎」下。
