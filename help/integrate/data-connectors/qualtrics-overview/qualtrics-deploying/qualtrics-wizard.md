---
description: 若要啓用整合，您必須在Data Connectors介面中完成Qualtrics整合精靈
seo-description: 若要啓用整合，您必須在Data Connectors介面中完成Qualtrics整合精靈
seo-title: 完成Adobe整合精靈
solution: Analytics
subtopic: Qualtrics
title: 完成Adobe整合精靈
topic: Data connectors
uuid: e065fba4-1Fe1-4e25-9c45-6c52dc81f81e
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Completing the Adobe Integration Wizard{#completing-the-adobe-integration-wizard}

若要啓用整合，您必須在Data Connectors介面中完成Qualtrics整合精靈

1. 導覽至資料連接器並啓動Qualtrics整合精靈。([Data connectors 說明](http://microsite.omniture.com/t2/help/en_US/genesis/)).
1. 選取您要用於此整合的報表套裝並提供名稱。

   完成整合精靈，提供下列步驟所述的資訊。1. **Wizard Step 1**

   | Email Address | 主要聯絡電子郵件地址。 |
   |---|---|
   | 說明 | (可選)此整合設定的說明。 |
   | Qualtrics組織ID | [查閱Qualtrics組織ID](../../qualtrics-overview/qualtrics-org-id.md#task-47ea30d6dcd24893986a5e5b8dcf5e96) |
   | Adobe SiteCatalyst Token | [產生Qualtrics Adobe Analytics Token](../../qualtrics-overview/qualtrics-token.md#task-e32eacbc91614008b84e6b2f0b92d372) |

1. **精靈步驟-變數映射**

   | Qualtrics回應清單 | 從報表套裝中選擇可用的清單變數。(您可能需要在「報表套裝管理器」中啓用新的ListVar)。 |
   |---|---|
   | Qualtrics回應ID | 從您的報表套裝中選擇可用的eVar或prop。(您可能需要在「報表套裝管理器」中啓用新的ListVar)。 |
   | 追蹤伺服器 | 提供追蹤Adobe Analytics資料的追蹤伺服器(網域)設定。`trackingServerSecure` 如果追蹤伺服器與標準追蹤伺服器設定不同，請使用此追蹤伺服器。 |
   | Qualtrics Survey提交 | 從報表套裝中選取可用事件(您可能需要從報表套裝管理器啓用新事件)。 |

1. **精靈步驟3**：一切都不需要，僅提供資訊。

   步驟結果1.**精靈步驟-匯出設定**

   | eVar | 選擇最多個eVar，以便匯出至Qualtrics |
   |---|---|
   | 事件 | 選取最多五個自訂事件，以便匯出至Qualtrics |
   | Prop | 選擇最多個Prop，以便匯出至Qualtrics |
   | 存取要求 | 檢查您要匯出至Qualtrics之標準度量和維度的方塊。The `visitor_id` is required to allow the export to function properly. |

1. **精靈步驟5**：檢閱組態，然後按一下 **[!UICONTROL 「立即啓動]**」。
