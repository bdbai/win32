---
title: PSM\_HWNDTOINDEX message
description: Takes the window handle of the property sheet page and returns its zero-based index. You can send this message explicitly or use the PropSheet\_HwndToIndex macro.
ms.assetid: 2eda4c95-95ed-4ebf-8245-c5b96aeb9075
keywords:
- PSM_HWNDTOINDEX message Windows Controls
topic_type:
- apiref
api_name:
- PSM_HWNDTOINDEX
api_location:
- Prsht.h
api_type:
- HeaderDef
ms.date: 05/31/2018
ms.topic: article
ms.author: windowssdkdev
ms.prod: windows
ms.technology: desktop
---

# PSM\_HWNDTOINDEX message

Takes the window handle of the property sheet page and returns its zero-based index. You can send this message explicitly or use the [**PropSheet\_HwndToIndex**](/windows/win32/Prsht/nf-prsht-propsheet_hwndtoindex?branch=master) macro.

## Parameters

<dl> <dt>

*wParam* 
</dt> <dd>

Handle to the page's window.

</dd> <dt>

*lParam* 
</dt> <dd>

Must be zero.

</dd> </dl>

## Return value

Returns the zero-based index of the property sheet page specified by *wParam* if successful. Otherwise, it returns -1.

## Requirements



|                                     |                                                                                    |
|-------------------------------------|------------------------------------------------------------------------------------|
| Minimum supported client<br/> | Windows Vista \[desktop apps only\]<br/>                                     |
| Minimum supported server<br/> | Windows Server 2003 \[desktop apps only\]<br/>                               |
| Header<br/>                   | <dl> <dt>Prsht.h</dt> </dl> |



 

 




