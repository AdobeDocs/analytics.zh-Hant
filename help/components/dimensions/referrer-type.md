---
title: 反向連結類型
description: 反向連結的類型，視訪客來自何處而定。
feature: Dimensions
exl-id: a6cfcbf4-cd08-4e7f-8e86-47488ceb0ea3
source-git-commit: e934de3938f013067d6bbd6b516b0444b0c9f782
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 88%

---

# 反向連結類型

「反向連結型別」[維度](overview.md)會報告訪客在點進哪些通用管道後到達您的網站。 Adobe 會維護每個維度項目的規則，不同於由您的組織維護各個管道之規則的[行銷管道](marketing-channel.md)。

## 將資料填入此維度中

此維度會參考 Adobe 內部的多個查閱表格。每個值都以點擊的[反向連結](referrer.md)為基礎，而這有賴於[內部 URL 篩選器](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md)。請確定反向連結維度和內部 URL 篩選器皆已正確設定。

## 維度項目

維度項目包含點擊的反向連結類型。特定值包括：

* **分類/建立書籤**：點擊沒有反向連結資料。
* **搜尋引擎**：反向連結來自於已認可、且包含關鍵字查詢字串的搜尋引擎。
* **交談AI工具**：反向連結來自於認可的交談AI工具。
* **社交網路：**：反向連結資料屬於 Adobe 認可的社交網路。
* **其他網站**：反向連結資料不屬於 Adobe 認可的搜尋引擎或社交網路。
* **無JavaScript**：反向連結來自於未啟用JavaScript的瀏覽器。
* **硬碟**：反向連結源自於訪客硬碟上的網頁本機複本。
* **電子郵件**：反向連結源自於具有通訊協定 `imap://` 或 `mail://` 的 URL。其中不包括線上電子郵件服務，因為這些服務通常使用 `https://` 通訊協定。

### 對話式人工智慧工具

下列清單列出Adobe所使用的「對話式AI工具」查詢表。 Adobe 提供此清單以便 Adobe Analytics 客戶使用。如果您想要建議 Adobe 在此清單中新增某個網域，請透過組織中的支援委派聯絡客戶服務。

* `https://chatgpt.com`
* `https://chat.com`
* `https://chat.openai.com`
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

### 社交網路

下列清單列出 Adobe 所使用的「社交網路」查閱表格。Adobe 提供此清單以便 Adobe Analytics 客戶使用。如果您想要建議 Adobe 在此清單中新增某個網域，請透過組織中的支援委派聯絡客戶服務。

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

當您在「反向連結類型」維度中檢視特定網域時，可能會發現某些您認為應列在「搜尋引擎」下方 (而非「其他網站」下方) 的網域。例如，您可能會在「其他網站」下方看到 `'google.com'`。

* **「搜尋引擎」維度項目中的搜尋引擎網域**：反向連結符合由 Adobe 分類為搜尋引擎的所有條件。反向連結網域是有效的搜尋引擎， *且*&#x200B;反向連結 URL 包含關鍵字查詢字串參數。
* **「其他網站」維度項目中的搜尋引擎網域**：反向連結 URL 不符合分類為搜尋引擎的所有條件。常見的範例包括搜尋以外的其他功能專用的子網域。例如，`mail.google.com` 或 `autos.yahoo.com` 不是搜尋引擎，但位於通常與搜尋相關聯的上層網域上。這些子網域不包含關鍵字查詢字串，正因如此，這些子網域才會包含在「其他網站」下，而非「搜尋引擎」下。
