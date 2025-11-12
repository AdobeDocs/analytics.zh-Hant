---
description: 了解 Analysis Workspace 的協助工具支援功能。
title: Analysis Workspace 的協助工具
feature: Workspace Basics
role: User, Admin
exl-id: 2bacbee8-097c-4fc5-8be4-7e4f284db08c
source-git-commit: ca84a5f807545d7196e2e0e90d3209c32d3fd789
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 100%

---


# Analysis Workspace 的協助工具

了解 Customer Journey Analytics 的主要分析工具 [!UICONTROL Analysis Workspace] 中的協助工具支援。

協助工具旨在讓產品適用於在視覺、聽覺、認知、運動能力和其他方面有障礙的人士。軟體產品的輔助功能範例包括：

* 螢幕閱讀器支援、
* 圖形等效文字、
* 鍵盤快速鍵、
* 將顯示顏色變更為高對比度，
* 及更多內容。

[!UICONTROL Analysis Workspace] 提供了一些方便使用的工具，包括：

## 鍵盤導覽

[!UICONTROL Analysis Workspace] 中的導覽可由上至下、由左至右運作。以下是可輔助協助工具的導覽元素：

* **[!UICONTROL Tab]** 鍵會啟用地標快速鍵，從而在 Workspace 中較大的區段之間移動。在左側面板中，**[!UICONTROL Tab]** 鍵也可讓您在不同的可拖曳選項之間移動。
* **[!UICONTROL Tab]** 鍵醒目標示一個元素後，◀◀︎ 和▶ ▶︎ 會在個別元素之間移動。
* **[!UICONTROL F6]** 鍵會導覽至專案中的第一個面板，並在該面板內的視覺效果之間移動。然後它會移到專案中的下一個面板，然後重複此程序。
* 套用焦點指標，讓視力不佳的鍵盤使用者能夠清楚看出目前取得焦點的 UI 元素。此指示器是具有焦點的藍色邊框面板。灰色背景表示最近選取的功能和功能內的選擇。在範例中，最近選取了「[!UICONTROL 元件]」和「頁面尺寸」。

  ![自由格式表格，顯示自由格式表格周圍藍色邊框的焦點指標。](assets/focus-indicator.png)

### 功能表列的鍵盤導覽

1. 按 Tab 鍵，直到抵達功能表列為止。
1. 使用箭頭鍵在選單和選單項目之間導覽。
1. 按 **[!UICONTROL Enter]** 以開啟選單或選取選單項目。
1. 使用 **[!UICONTROL Esc]** 以關閉選單。

### 拖放互動的鍵盤導覽

[!UICONTROL Analysis Workspace] 是著重於拖放功能的使用者介面。但使用者也可改用鍵盤新增元件：

1. 以 Tab 切換至左側面板中的元件。
1. 按 **[!UICONTROL Enter]** 以進行選取。
1. 使用方向鍵導覽至您要放置元件的區域。
1. 按 **[!UICONTROL Enter]** 以放置元件。

### 鍵盤快速鍵 (熱鍵)

[!UICONTROL Analysis Workspace] 提供一組豐富的[鍵盤快速鍵 (快速鍵)](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md)，讓工作流程更加順暢。

## 支援螢幕助讀程式和螢幕放大鏡

螢幕助讀程式會讀出顯示在電腦螢幕上的文字。它還讀取非文字資訊，例如應用程式按鈕標籤或影像說明。

## 調色盤和對比

[!UICONTROL Analysis Workspace] 致力於達到 WCAG 2.1 AA 的要求，包括色彩對比的要求。

此外，使用者可在&#x200B;**[!UICONTROL 專案]** > **[!UICONTROL 專案設定]** > [專案調色盤](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md)下，針對專案設定自己偏好的調色盤。

## 所需的驗證

建置元件、視覺效果或面板，儲存時會驗證必填欄位。如果必要欄位未通過驗證，則會以紅色列出並顯示錯誤圖示。書面說明解釋需要修復的內容。

![區段產生器和錯誤驗證指標。](assets/error-validation.png)

## 支援作業系統協助工具功能

Analysis Workspace 支援內建的 Windows 和 macOS 協助工具功能，例如高對比模式、相黏鍵和慢速鍵/篩選鍵。此外也提供作業系統使用者介面的相關資訊，以透過輔助技術支援互動，包括螢幕助讀程式 (例如 macOS 的 VoiceOver 和 Windows 上的 NVDA)。


<!--

# Accessibility in Analysis Workspace

Learn about accessibility support in [!UICONTROL Analysis Workspace], the premier analysis tool for Adobe Analytics. 

Accessibility refers to making products usable for people with visual, auditory, cognitive, motor, and other disabilities. Examples of accessibility features for software products include screen reader support, text equivalents for graphics, keyboard shortcuts, change of display colors to high contrast, and so on. 

[!UICONTROL Analysis Workspace] provides some tools that make it accessible to use, including:

## Navigate [!UICONTROL Workspace] using the keyboard

Navigation in [!UICONTROL Analysis Workspace] works top > down, and left > right. The following navigational elements facilitate accessibility:

* The `Tab` key enables landmark shortcuts, moving between larger sections within Workspace. In the left rail, `Tab` also enables you to move from one draggable option to the next.
* The `left/right arrows` move between individual elements after `Tab` has highlighted it. 
* The `F6` navigates to the first panel in the project and  moves between the visualizations within that panel. Then, it moves to the next panel in the project and repeats. 
* We apply focus indicators so that sighted keyboard users have a clear indication of which UI element currently has focus. The indicator is a blue border around the selected element.

    ![Focus Indicator](assets/focus-indicator.png)

### Keyboard navigation for the menu bar 

1. Tab until you have reached the menu bar.
1. Use left/right arrow keys to navigate to the menu you want.
1. Press `Enter` to select the menu and show its options.
1. Use up/down arrow keys to navigate to the menu option you want.
1. Press `Enter` to select the option.

### Keyboard navigation for drag & drop interactions 

[!UICONTROL Analysis Workspace] is a drag & drop user interface. However, users can add components using the keyboard instead:

1. Tab to a component in the left rail.
1. Press `Enter` to select.
1. Use arrow keys to navigate to the area where you want to drop the component.
1. Press `Enter` to place the component.

### Keyboard shortcuts (hotkeys) 

[!UICONTROL Analysis Workspace] offers a rich set of [keyboard shortcuts](/help/analyze/analysis-workspace/build-workspace-project/fa-shortcut-keys.md) for a more seamless workflow. Some common shortcuts for navigation, analysis creation, and insight democratization are listed below. 

#### Navigation

| Shortcut | Action |
| --- | --- |
| `[Alt + Shift + 1 / 2 / 3]` | Jump to different rails: [!UICONTROL Panels], [!UICONTROL Visualizations], or [!UICONTROL Components] |
| `[Alt + Left / Right]` | Navigate between panels |
| `[Alt + M]` | Collapse/expand all panels |
| `[Alt + Ctrl + M]` | Collapse/expand active panel |
| `[Ctrl + /]` | Search left rail |

#### Analysis creation

| Shortcut | Action |
| --- | --- |
| `[Alt + 1]` | New freeform table |
| `[Ctrl + Shift + C]` | New calculated metric |
| `[Ctrl + Shift + D]` | New date range |
| `[Ctrl + Shift + E]` | New segment |
| `[Ctrl + Z]` | Undo |
| `[Component drag + Shift]` | Create a drop-down filter |

#### Democratization

| Shortcut | Action |
| --- | --- |
| `[Ctrl + S]` | Save |
| `[Ctrl + Shift + G]` | Curate |
| `[Ctrl + G]` | Share |
| `[Alt + Shift + S]` | Schedule |
| `[Alt + L]` | Get link to project |
| `[Ctrl + Shift + B]` | Download PDF |

## Support for screen readers and screen magnifiers

A screen reader reads text that appears on the computer screen. It also reads non-textual information, such as button labels or image descriptions in the application, provided in accessibility tags or attributes.  

## Color palettes & contrast  

[!UICONTROL Analysis Workspace] strives for WCAG 2.1 AA conformance, including requirements for color contrast. 

In addition, users can set their own preferred color palette for a project under **[!UICONTROL Project]** > **[!UICONTROL Project settings]** > [Project color palette](/help/analyze/analysis-workspace/build-workspace-project/color-palettes.md). 

## Required field validation in component builders 

When building a component, required fields are validated when you save. If a required field does not pass validation, it will be outlined in red with an error icon. A written description appears of the issue that needs to be fixed.  

Once a component is fully validated, pressing `Save` closes the builder. 

![Error validation](assets/error-validation.png)

## Support for operating system accessibility features  

Analysis Workspace supports built-in MS Windows and macOS accessibility features like high-contrast mode, sticky keys, and slow keys/filter keys. It also provides information about the user interface to the operating system to enable interaction with assistive technologies, including screen readers such as VoiceOver for macOS and NVDA on Windows.

-->