---
title: 反向連結類型
description: 反向連結的類型，視訪客的來源而定。
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 0%

---


# 反向連結類型

「反向連結類型」維度會報告訪客點進哪些通用渠道來到您的網站。 Adobe會維護每個維度項目的規則，而 [Marketing渠道](marketing-channel.md)，您的組織會維護每個渠道的規則。

## 將資料填入此維度

此維度會參照Adobe內部的多個查閱表格。 每個值都以點擊的反 [向連結](referrer.md) 為基礎，這取決於 [內部URL篩選器](/help/admin/admin/internal-url-filter-admin.md)。 請確定已正確設定反向連結維度和內部URL篩選器。

## 維度項目

維度項目包含點擊的反向連結類型。 特定值包括：

* **分類／建立書籤**: 點擊沒有反向連結資料。
* **搜尋引擎**: 反向連結來自已識別的搜尋引擎，其中包含關鍵字查詢字串。
* **社交網路：**: 反向連結資料屬於Adobe認可的社交網路。
* **其他網站**: 反向連結資料不屬於Adobe識別的搜尋引擎或社交網路。
* **硬碟**: 反向連結源自訪客硬碟上網頁的本機副本。
* **電子郵件**: 反向連結來源於通訊協定為或的 `imap://` URL `mail://`。 不包含線上電子郵件服務，因為這些服務通常使用 `https://` 通訊協定。

### 社交網路

下列清單會參照Adobe使用的「社交網路」查閱表格。 Adobe禮節性地提供此清單給Adobe Analytics客戶。 如果您想要建議Adobe將網域新增至此清單，請讓組織中的支援委派聯絡客戶服務。

>[!NOTE]
>
>此清單與 [Marketing Channel處理規則中社交網路的預設清單不同](../c-marketing-channels/c-rules.md)。

* `12seconds.tv`
* `t.163.com`
* `4travel.jp`
* `advogato.org`
* `ameba.jp`
* `anobii.com`
* `asmallworld.net`
* `avforums.com`
* `backtype.com`
* `badoo.com`
* `bebo.com`
* `bigadda.com`
* `bigtent.com`
* `biip.no`
* `blackplanet.com`
* `blogspot.com`
* `blogster.com`
* `blomotion.jp`
* `bolt.com`
* `brightkite.com`
* `buzznet.com`
* `cafemom.com`
* `care2.com`
* `classmates.com`
* `cloob.com`
* `collegeblender.com`
* `cyworld.co.kr`
* `cyworld.com.cn`
* `dailymotion.com`
* `yozm.daum.net`
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
* `goodreads.com`
* `plus.google.com`
* `plus.url.google.com`
* `grono.net`
* `habbo.com`
* `hatena.ne.jp`
* `t.hexun.com`
* `hi5.com`
* `hyves.nl`
* `ibibo.com`
* `identi.ca`
* `t.ifeng.com`
* `imeem.com`
* `hotnews.infoseek.co.jp`
* `instagram.com`
* `intensedebate.com`
* `irc-galleria.net`
* `iwiw.hu`
* `jaiku.com`
* `kaixin001.com`
* `kaixin002.com`
* `kakaku.com`
* `kanshin.com`
* `kozocom.com`
* `last.fm`
* `linkedin.com`
* `livejournal.com`
* `lnkd.in`
* `me2day.net`
* `meetup.com`
* `mister-wong.com`
* `mixi.jp`
* `mixx.com`
* `mouthshut.com`
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
* `t.people.com.cn`
* `photobucket.com`
* `pinterest.com (and all international domains)`
* `plaxo.com`
* `plurk.com`
* `po.st`
* `t.qq.com`
* `mp.weixin.qq.com`
* `boards.qwant.com`
* `reddit.com`
* `renren.com`
* `blog.seesaa.jp`
* `t.sina.com.cn`
* `skyrock.com`
* `slideshare.net`
* `smcb.jp`
* `smugmug.com`
* `t.sohu.com`
* `sonico.com`
* `studivz.net`
* `stumbleupon.com`
* `t.co`
* `tabelog.com`
* `tagged.com`
* `taringa.net`
* `thefancy.com`
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
* `weibo.com`
* `weourfamily.com`
* `wer-kennt-wen.de`
* `wordpress.com`
* `xanga.com`
* `xing.com`
* `answers.yahoo.com`
* `yammer.com`
* `yaplog.jp`
* `yelp.com`
* `yelp.co.uk`
* `youku.com`
* `youtube.com`
* `yuku.com`
* `zooomr.com`
* `zhihu.com`

### 「其他網站」維度項目中的搜尋引擎

當您在「反向連結類型」維度中檢視特定網域時，「搜尋引擎」下方會列出一些網域，而「其他網站」下方會列出一些網域。 例如，您可能會在「其 `'google.com'` 他網站」下方看到。

* **「搜尋引擎」維度項目中的搜尋引擎網域**: 反向連結符合Adobe分類為搜尋引擎的所有條件。 反向連結網域是有效的搜尋引擎， *而反向連結* URL包含關鍵字查詢字串參數。
* **「其他網站」維度項目中的搜尋引擎網域**: 反向連結URL未符合所有要分類為搜尋引擎的條件。 常見的範例包括除了搜尋外，其他功能專用的子網域。 例如， `mail.google.com` 或不 `autos.yahoo.com` 是搜尋引擎，但位於通常與搜尋相關聯的頂層網域。 這些子網域不包含關鍵字查詢字串，這就是為什麼這些子網域會包含在「其他網站」而非「搜尋引擎」下。
