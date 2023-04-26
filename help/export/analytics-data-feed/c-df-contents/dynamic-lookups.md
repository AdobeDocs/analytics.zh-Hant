---
title: 動態查閱
description: 了解動態查閱的功能及啟用方式。 包括電信業者、行動屬性和作業系統類型。
source-git-commit: b6084fc34165ea602fce616e13b3adfcd7bdfdbd
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# 動態查閱

動態查閱可讓您在資料摘要中接收其他無法使用的查閱檔案。 此設定可讓下列查閱表格與每個資料摘要檔案一併傳送：

* **電信業者名稱**:提供 `carrier` 欄。 包含的檔案名為 `carrier.tsv`.
* **行動屬性**:提供 `mobile_id` 欄，包括每個行動裝置追蹤的所有功能。 包含的檔案名為 `mobile_attributes.tsv`.
* **作業系統類型**:提供 `os` 欄。 兩者 `operating_systems.tsv` 和 `operating_system_type.tsv` 使用 `os` 欄作為索引鍵，不過 `operating_system_type.tsv` 是動態查閱。

## 啟用動態查閱

若要接收上述查閱檔案，您必須符合下列所有必要條件：

* 資料摘要中必須包含索引鍵欄。
   * 針對 `carrier.tsv`，您必須包含 `carrier`.
   * 針對 `mobile_attributes.tsv`，您必須包含 `mobile_id`.
   * 針對 `operating_system_type.tsv`，您必須包含 `os`.
* 下列欄必須 **已排除**. 如果資料摘要中包含其中任何一欄，則不會包含其他查閱表格。
   * `user_agent`
   * `ch_hdr`
   * `ch_js`

當您的資料摘要符合欄包含和排除需求時，請聯絡客戶服務以取得資料摘要ID，並請求啟用動態查閱。

## 查閱標題參考

這些查閱檔案的欄標題不會隨著時間而變更，因此每個資料摘要檔案中不會包含標題。 使用這些欄標題作為參考，或下載其各自的 `.tsv` 檔案。

+++**電信業者名稱**
下載 [carrier_headers.tsv](assets/carrier_headers.tsv) 或參考下方標題。

`carrier`
`Carrier Name`
+++

+++**行動屬性**
下載 [mobile_attributes_headers.tsv](assets/mobile_attributes_headers.tsv) 或參考下方標題。

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

+++**作業系統類型**
下載 [operating_system_type_headers.tsv](assets/operating_system_type_headers.tsv) 或參考下方標題。

`os`
`Operating System Type`
+++