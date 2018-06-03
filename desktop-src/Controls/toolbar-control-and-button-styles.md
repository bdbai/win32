---
title: Toolbar Control and Button Styles
description: The following window styles are specific to toolbars.
ms.assetid: 75dc0c2c-6d1d-4b13-b0df-2cc541a9b1bb
topic_type:
- apiref
api_name:
- TBSTYLE_ALTDRAG
- TBSTYLE_CUSTOMERASE
- TBSTYLE_FLAT
- TBSTYLE_LIST
- TBSTYLE_REGISTERDROP
- TBSTYLE_TOOLTIPS
- TBSTYLE_TRANSPARENT
- TBSTYLE_WRAPABLE
- BTNS_AUTOSIZE
- BTNS_BUTTON
- BTNS_CHECK
- BTNS_CHECKGROUP
- BTNS_DROPDOWN
- BTNS_GROUP
- BTNS_NOPREFIX
- BTNS_SEP
- BTNS_SHOWTEXT
- BTNS_WHOLEDROPDOWN
- TBSTYLE_AUTOSIZE
- TBSTYLE_BUTTON
- TBSTYLE_CHECK
- TBSTYLE_CHECKGROUP
- TBSTYLE_DROPDOWN
- TBSTYLE_GROUP
- TBSTYLE_NOPREFIX
- TBSTYLE_SEP
api_location:
- CommCtrl.h
api_type:
- HeaderDef
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# Toolbar Control and Button Styles

The following window styles are specific to toolbars. They are combined with other window styles when the toolbar is created.

**Note** For Common Controls [version 6.00](common-control-versions.md), if a [visual style](themes-overview.md) is being used with the toolbar, buttons are always transparent regardless of the style setting. Otherwise, transparency behavior is normal as indicated by the use of the TBSTYLE\_FLAT or TBSTYLE\_TRANSPARENT style.

> [!Note]  
> Comctl32.dll version 6 is not redistributable but it is included in Windows. To use Comctl32.dll version 6, specify it in a manifest. For more information on manifests, see [Enabling Visual Styles](cookbook-overview.md).

 



| Constant                                                                                                                                                                           | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="TBSTYLE_ALTDRAG"></span><span id="tbstyle_altdrag"></span><dl> <dt>**TBSTYLE\_ALTDRAG**</dt> </dl>                | Allows users to change a toolbar button's position by dragging it while holding down the ALT key. If this style is not specified, the user must hold down the SHIFT key while dragging a button. Note that the [**CCS\_ADJUSTABLE**](https://www.bing.com/search?q=**CCS\_ADJUSTABLE**) style must be specified to enable toolbar buttons to be dragged.<br/>                                                                                                                                                                               |
| <span id="TBSTYLE_CUSTOMERASE"></span><span id="tbstyle_customerase"></span><dl> <dt>**TBSTYLE\_CUSTOMERASE**</dt> </dl>    | [Version 4.70](common-control-versions.md). Generates [NM\_CUSTOMDRAW](nm-customdraw.md) notification codes when the toolbar processes [**WM\_ERASEBKGND**](https://msdn.microsoft.com/library/windows/desktop/ms648055) messages.<br/>                                                                                                                                                                                                                                                                                                                                 |
| <span id="TBSTYLE_FLAT"></span><span id="tbstyle_flat"></span><dl> <dt>**TBSTYLE\_FLAT**</dt> </dl>                         | [Version 4.70](common-control-versions.md). Creates a flat toolbar. In a flat toolbar, both the toolbar and the buttons are transparent and hot-tracking is enabled. Button text appears under button bitmaps. To prevent repainting problems, this style should be set before the toolbar control becomes visible. <br/>                                                                                                                                                                                                         |
| <span id="TBSTYLE_LIST"></span><span id="tbstyle_list"></span><dl> <dt>**TBSTYLE\_LIST**</dt> </dl>                         | [Version 4.70](common-control-versions.md). Creates a flat toolbar with button text to the right of the bitmap. Otherwise, this style is identical to **TBSTYLE\_FLAT**. To prevent repainting problems, this style should be set before the toolbar control becomes visible.<br/>                                                                                                                                                                                                                                                |
| <span id="TBSTYLE_REGISTERDROP"></span><span id="tbstyle_registerdrop"></span><dl> <dt>**TBSTYLE\_REGISTERDROP**</dt> </dl> | [Version 4.71](common-control-versions.md). Generates [TBN\_GETOBJECT](tbn-getobject.md) notification codes to request drop target objects when the cursor passes over toolbar buttons.<br/>                                                                                                                                                                                                                                                                                                                                     |
| <span id="TBSTYLE_TOOLTIPS"></span><span id="tbstyle_tooltips"></span><dl> <dt>**TBSTYLE\_TOOLTIPS**</dt> </dl>             | Creates a tooltip control that an application can use to display descriptive text for the buttons in the toolbar.<br/>                                                                                                                                                                                                                                                                                                                                                                                                             |
| <span id="TBSTYLE_TRANSPARENT"></span><span id="tbstyle_transparent"></span><dl> <dt>**TBSTYLE\_TRANSPARENT**</dt> </dl>    | [Version 4.71](common-control-versions.md). Creates a transparent toolbar. In a transparent toolbar, the toolbar is transparent but the buttons are not. Button text appears under button bitmaps. To prevent repainting problems, this style should be set before the toolbar control becomes visible.<br/>                                                                                                                                                                                                                      |
| <span id="TBSTYLE_WRAPABLE"></span><span id="tbstyle_wrapable"></span><dl> <dt>**TBSTYLE\_WRAPABLE**</dt> </dl>             | Creates a toolbar that can have multiple lines of buttons. Toolbar buttons can "wrap" to the next line when the toolbar becomes too narrow to include all buttons on the same line. When the toolbar is wrapped, the break will occur on either the rightmost separator or the rightmost button if there are no separators on the bar. This style must be set to display a vertical toolbar control when the toolbar is part of a vertical [rebar control](rebar-controls.md). This style cannot be combined with CCS\_VERT.<br/> |



**Note:** A toolbar button can have a combination of the following styles. To specify a button style, set the appropriate flags in the **fsStyle** member of the button's [**TBBUTTON**](/windows/desktop/api/Commctrl/ns-commctrl-_tbbutton) structure. Not all styles can be combined.

For Shell version 4.72 and earlier, both window and button style flags had the form TBSTYLE\_XXX. If you are compiling an application with [version 4.72](common-control-versions.md) or earlier of Commctrl.h, you must use the TBSTYLE\_XXX button style flags. For version 5.80 and later, all button styles have the form BTNS\_XXX. All of the TBSTYLE\_XXX values have equivalent BTNS\_XXX values, with the same meaning and numerical value. For convenience, both forms are given in the following table.



| Constant                                                                                                                                                                     | Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span id="BTNS_AUTOSIZE"></span><span id="btns_autosize"></span><dl> <dt>**BTNS\_AUTOSIZE**</dt> </dl>                | [Version 5.80](common-control-versions.md). Specifies that the toolbar control should not assign the standard width to the button. Instead, the button's width will be calculated based on the width of the text plus the image of the button. Use the equivalent style flag, **TBSTYLE\_AUTOSIZE**, for version 4.72 and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| <span id="BTNS_BUTTON"></span><span id="btns_button"></span><dl> <dt>**BTNS\_BUTTON**</dt> </dl>                      | [Version 5.80](common-control-versions.md). Creates a standard button. Use the equivalent style flag, **TBSTYLE\_BUTTON**, for version 4.72 and earlier. This flag is defined as 0, and should be used to signify that no other flags are set.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| <span id="BTNS_CHECK"></span><span id="btns_check"></span><dl> <dt>**BTNS\_CHECK**</dt> </dl>                         | [Version 5.80](common-control-versions.md). Creates a dual-state push button that toggles between the pressed and nonpressed states each time the user clicks it. The button has a different background color when it is in the pressed state. Use the equivalent style flag, **TBSTYLE\_CHECK**, for version 4.72 and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
| <span id="BTNS_CHECKGROUP"></span><span id="btns_checkgroup"></span><dl> <dt>**BTNS\_CHECKGROUP**</dt> </dl>          | [Version 5.80](common-control-versions.md). Creates a button that stays pressed until another button in the group is pressed, similar to option buttons (also known as radio buttons). It is equivalent to combining BTNS\_CHECK and BTNS\_GROUP. Use the equivalent style flag, **TBSTYLE\_CHECKGROUP**, for version 4.72 and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| <span id="BTNS_DROPDOWN"></span><span id="btns_dropdown"></span><dl> <dt>**BTNS\_DROPDOWN**</dt> </dl>                | [Version 5.80](common-control-versions.md). Creates a drop-down style button that can display a list when the button is clicked. Instead of the WM\_COMMAND message used for normal buttons, drop-down buttons send a [TBN\_DROPDOWN](tbn-dropdown.md) notification code. An application can then have the notification handler display a list of options. Use the equivalent style flag, **TBSTYLE\_DROPDOWN**, for version 4.72 and earlier. <br/> If the toolbar has the [**TBSTYLE\_EX\_DRAWDDARROWS**](https://www.bing.com/search?q=**TBSTYLE\_EX\_DRAWDDARROWS**) extended style, drop-down buttons will have a drop-down arrow displayed in a separate section to their right. If the arrow is clicked, a TBN\_DROPDOWN notification code will be sent. If the associated button is clicked, a WM\_COMMAND message will be sent.<br/> |
| <span id="BTNS_GROUP"></span><span id="btns_group"></span><dl> <dt>**BTNS\_GROUP**</dt> </dl>                         | [Version 5.80](common-control-versions.md). When combined with BTNS\_CHECK, creates a button that stays pressed until another button in the group is pressed. Use the equivalent style flag, **TBSTYLE\_GROUP**, for version 4.72 and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| <span id="BTNS_NOPREFIX"></span><span id="btns_noprefix"></span><dl> <dt>**BTNS\_NOPREFIX**</dt> </dl>                | [Version 5.80](common-control-versions.md). Specifies that the button text will not have an accelerator prefix associated with it. Use the equivalent style flag, **TBSTYLE\_NOPREFIX**, for version 4.72 and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| <span id="BTNS_SEP"></span><span id="btns_sep"></span><dl> <dt>**BTNS\_SEP**</dt> </dl>                               | [Version 5.80](common-control-versions.md). Creates a separator, providing a small gap between button groups. A button that has this style does not receive user input. Use the equivalent style flag, **TBSTYLE\_SEP**, for version 4.72 and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
| <span id="BTNS_SHOWTEXT"></span><span id="btns_showtext"></span><dl> <dt>**BTNS\_SHOWTEXT**</dt> </dl>                | [Version 5.81](common-control-versions.md). Specifies that button text should be displayed. All buttons can have text, but only those buttons with the BTNS\_SHOWTEXT button style will display it. This button style must be used with the **TBSTYLE\_LIST** style and the [**TBSTYLE\_EX\_MIXEDBUTTONS**](https://www.bing.com/search?q=**TBSTYLE\_EX\_MIXEDBUTTONS**) extended style. If you set text for buttons that do not have the BTNS\_SHOWTEXT style, the toolbar control will automatically display it as a tooltip when the cursor hovers over the button. This feature allows your application to avoid handling the [TBN\_GETINFOTIP](tbn-getinfotip.md) or [TTN\_GETDISPINFO](ttn-getdispinfo.md) notification code for the toolbar.<br/>                                                                                           |
| <span id="BTNS_WHOLEDROPDOWN"></span><span id="btns_wholedropdown"></span><dl> <dt>**BTNS\_WHOLEDROPDOWN**</dt> </dl> | [Version 5.80](common-control-versions.md). Specifies that the button will have a drop-down arrow, but not as a separate section. Buttons with this style behave the same, regardless of whether the [**TBSTYLE\_EX\_DRAWDDARROWS**](https://www.bing.com/search?q=**TBSTYLE\_EX\_DRAWDDARROWS**) extended style is set.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| <span id="TBSTYLE_AUTOSIZE"></span><span id="tbstyle_autosize"></span><dl> <dt>**TBSTYLE\_AUTOSIZE**</dt> </dl>       | Equivalent to **BTNS\_AUTOSIZE**. Use TBSTYLE\_AUTOSIZE for [version 4.72](common-control-versions.md) and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| <span id="TBSTYLE_BUTTON"></span><span id="tbstyle_button"></span><dl> <dt>**TBSTYLE\_BUTTON**</dt> </dl>             | Equivalent to **BTNS\_BUTTON**. Use TBSTYLE\_BUTTON for [version 4.72](common-control-versions.md) and earlier. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
| <span id="TBSTYLE_CHECK"></span><span id="tbstyle_check"></span><dl> <dt>**TBSTYLE\_CHECK**</dt> </dl>                | Equivalent to **BTNS\_CHECK**. Use TBSTYLE\_CHECK for [version 4.72](common-control-versions.md) and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           |
| <span id="TBSTYLE_CHECKGROUP"></span><span id="tbstyle_checkgroup"></span><dl> <dt>**TBSTYLE\_CHECKGROUP**</dt> </dl> | Equivalent to **BTNS\_CHECKGROUP**. Use TBSTYLE\_CHECKGROUP for [version 4.72](common-control-versions.md) and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 |
| <span id="TBSTYLE_DROPDOWN"></span><span id="tbstyle_dropdown"></span><dl> <dt>**TBSTYLE\_DROPDOWN**</dt> </dl>       | Equivalent to **BTNS\_DROPDOWN**. Use TBSTYLE\_DROPDOWN for [version 4.72](common-control-versions.md) and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| <span id="TBSTYLE_GROUP"></span><span id="tbstyle_group"></span><dl> <dt>**TBSTYLE\_GROUP**</dt> </dl>                | Equivalent to **BTNS\_GROUP**. Use TBSTYLE\_GROUP for [version 4.72](common-control-versions.md) and earlier. <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| <span id="TBSTYLE_NOPREFIX"></span><span id="tbstyle_noprefix"></span><dl> <dt>**TBSTYLE\_NOPREFIX**</dt> </dl>       | Equivalent to **BTNS\_NOPREFIX**. Use TBSTYLE\_NOPREFIX for [version 4.72](common-control-versions.md) and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
| <span id="TBSTYLE_SEP"></span><span id="tbstyle_sep"></span><dl> <dt>**TBSTYLE\_SEP**</dt> </dl>                      | Equivalent to **BTNS\_SEP**. Use TBSTYLE\_SEP for [version 4.72](common-control-versions.md) and earlier.<br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               |



## Requirements



|                   |                                                                                       |
|-------------------|---------------------------------------------------------------------------------------|
| Header<br/> | <dl> <dt>CommCtrl.h</dt> </dl> |



 

 




