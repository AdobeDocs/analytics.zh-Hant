---
title: 動態查詢
description: 瞭解什麼是動態查詢以及如何啟用動態查詢。 包括電信業者、行動屬性和作業系統型別。
exl-id: 12327239-06a2-4092-b27d-b94da39abf30
feature: Data Feeds
source-git-commit: 6b8366b451be1612331f517ee80fd57744deafdc
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 1%

---

# 動態查詢

動態查詢可讓您在資料摘要中接收其他查詢檔案（若未提供）。 此設定可讓以下查閱表格隨每個資料摘要檔案一起傳送：

* **電信業者名稱**：為提供額外的內容 `carrier` 欄。 包含的檔案名稱為 `carrier.tsv`.
* **行動屬性**：為提供額外的內容 `mobile_id` 欄，包含針對每個行動裝置追蹤的所有功能。 包含的檔案名稱為 `mobile_attributes.tsv`.
* **作業系統型別**：提供替代的內容 `os` 欄。 兩者 `operating_systems.tsv` 和 `operating_system_type.tsv` 使用 `os` 欄做為索引鍵，但僅限 `operating_system_type.tsv` 是動態查詢。

## 啟用動態查詢

若要接收上述的查閱檔案，您必須符合下列所有必要條件：

* 資料摘要中必須包含索引鍵資料行。
   * 的 `carrier.tsv`，您必須包含 `carrier`.
   * 的 `mobile_attributes.tsv`，您必須包含 `mobile_id`.
   * 的 `operating_system_type.tsv`，您必須包含 `os`.
* 下列欄必須 **已排除**. 若資料摘要中包含這些欄中的任何一欄，則 `mobile_attributes.tsv` 動態查詢不包含在內。
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

資料摘要符合欄包含和排除要求後，請聯絡客戶服務以取得資料摘要ID，並要求啟用動態查閱。

## 查詢標頭參考

這些查詢檔案的欄標題不會隨著時間改變，因此標題不會包含在每個資料摘要檔案中。 使用這些欄標題作為參考，或下載它們各自的標題 `.tsv` 檔案。

+++**電信業者名稱**
下載 [carrier_headers.tsv](assets/carrier_headers.tsv) 或參考下方的標題。

`carrier`
`Carrier Name`
+++

+++**行動屬性**
下載 [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) 或參考下方的標題。

`mobile_id`
`Manufacturer`
`Device`
`Device Type`
`Operating System`
`Diagonal Screen Size`
`Screen Height`
`Screen Width`
`Cookie Support`
`Color Depth`
`MP3 Audio Support`
`AAC Audio Support`
`AMR Audio Support`
`Midi Monophonic Audio Support`
`Midi Polyphonic Audio Support`
`QCELP Audio Support`
`GIF87 Image Support`
`GIF89a Image Support`
`PNG Image Support`
`JPG Image Support`
`3GPP Video Support`
`MPEG4 Video Support`
`3GPP2 Video Support`
`WMV Video Support`
`MPEG4 Part 2 Video Support`
`Stream MP4 AAC LC Video Support`
`Stream 3GP H264 Level 10b Video Support`
`Stream 3GP AAC LC Video Support`
`3GP AAC LC Video Support`
`Stream MP4 H264 Level 11 Video Support`
`Stream MP4 H264 Level 13 Video Support`
`Stream 3GP H264 Level 12 Video Support`
`Stream 3GP H264 Level 11 Video Support`
`Stream 3GP H264 Level 10 Video Support`
`Stream 3GP H264 Level 13 Video Support`
`3GP AMR NB Video Support`
`3GP AMR WB Video Support`
`MP4 H264 Level 11 Video Support`
`3GP H263 Video Support`
`MP4 H264 Level 13 Video Support`
`Stream 3GP H263 Video Support`
`Stream 3GP AMR WB Video Support`
`3GP H264 Level 10b Video Support`
`MP4 ACC LC Video Support`
`Stream 3GP AMR NB Video Support`
`3GP H264 Level 10 Video Support`
`3GP H264 Level 13 Video Support`
`3GP H264 Level 11 Video Support`
`3GP H264 Level 12 Video Support`
`Stream HTTP Live Streaming Video Support`
+++

+++**作業系統型別**
下載 [operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) 或參考下方的標題。

`os`
`Operating System Type`
+++
