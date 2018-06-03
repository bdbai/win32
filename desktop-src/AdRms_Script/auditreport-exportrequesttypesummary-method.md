---
Description: Generates a report for the number of total, successful, and failed requests of all types.
audience: developer
author: REDMOND\\markl
manager: REDMOND\\mbaldwin
ms.assetid: 261ae105-9261-4173-8006-97c995c76c94
ms.prod: windows-server-dev
ms.technology: active-directory-rights-management
ms.tgt_platform: multiple
title: AuditReport.ExportRequestTypeSummary method
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# AuditReport.ExportRequestTypeSummary method

The **ExportRequestTypeSummary** method generates a report for the number of total, successful, and failed requests of all types.

## Syntax


```VB
AuditReport.ExportRequestTypeSummary( _
  ByVal languageId, _
  ByVal start, _
  ByVal end, _
  ByVal filePath, _
  ByVal fileType _
)
```



## Parameters

<dl> <dt>

*languageId* 
</dt> <dd>

An integer that contains the locale ID (LCID) of the report language. For example, the LCID for U.S. English is 1033. For a complete list of the LCIDs supported by Microsoft, see [List of Locale ID (LCID) Values as Assigned by Microsoft](http://go.microsoft.com/fwlink/p/?linkid=63028).

</dd> <dt>

*start* 
</dt> <dd>

A **DateTime** value that contains the beginning time for the report.

</dd> <dt>

*end* 
</dt> <dd>

A **DateTime** value that contains the ending time for the report.

</dd> <dt>

*filePath* 
</dt> <dd>

A **String** value that contains the report file path.

</dd> <dt>

*fileType* 
</dt> <dd>

An integer that contains the export file type. This can be one of the following values.

<dt>

0
</dt> <dd>

Microsoft Excel (.xls) file.

</dd> <dt>

2
</dt> <dd>

Portable Document Format (PDF) file.

</dd> </dl> </dd> </dl>

## Return value

This method returns a Boolean value. **True** specifies that a report was generated. **False** specifies that no report could be generated for the given input.

## Remarks

The following types of requests are typical:

-   Retrieve a server licensor certificate.
-   Retrieve a client licensor certificate.
-   Find service locations.
-   Acquire an end-user license.
-   Retrieve a preproduction certificate.
-   Retrieve a production certificate.
-   Sign an issuance license.
-   Retrieve templates and template information.

## Examples


```VB
DIM config_manager
DIM admin_role

' *******************************************************************
' Create and initialize a ConfigurationManager object.

SUB InitObject()

  CALL WScript.Echo( "Create ConfigurationManager object...")
  SET config_manager = CreateObject _
    ("Microsoft.RightsManagementServices.Admin.ConfigurationManager")      
  CheckError()
    
  CALL WScript.Echo( "Initialize...")
  admin_role=config_manager.Initialize(false,"localhost",80,"","","")
  CheckError()

END SUB

' *******************************************************************
' Generate a RequestTypeSummary report.
'
' Variables:
'    auditReport - AuditReport object
'    lcid        - 1033 is the U.S. English LCID
'    endDate     - Today's date
'    startDate   - Ten days prior to the end date
'    outFile     - Output file path
'    fileType    - Zero (0) represents an Excel (.xls) file

SUB CreateReport()

  DIM auditReport
  DIM lcid
  DIM endDate
  DIM startDate
  DIM outFile
  DIM fileType

  lcid = 1033
  endDate = Now
  startDate = DateAdd("d", -10, endDate)
  outFile = "c:\RequestTypeSummary.xls"
  fileType = 0

  ' Create an AuditReport object.
  SET auditReport = _
          config_manager.AuditReport
  CheckError()

  ' Generate the report.
  CALL auditReport.ExportRequestTypeSummary( _
      lcid, _ 
      startDate, _ 
      endDate, _ 
      outFile, _ 
      fileType)
  CheckError()

END SUB

' *******************************************************************
' Error checking function.

FUNCTION CheckError()
  CheckError = Err.number
  IF Err.number <> 0 THEN
    CALL WScript.Echo( vbTab & "*****Error Number: " _
                       & Err.number _
                       & " Desc:" _
                       & Err.Description _
                       & "*****")
    WScript.StdErr.Write(Err.Description)
    WScript.Quit( Err.number )
  END IF
END FUNCTION

' *******************************************************************
' Generate a runtime error.

SUB RaiseError(errId, desc)
  CALL Err.Raise( errId, "", desc )
  CheckError()
END SUB
```



## Requirements



|                                     |                                                                                                                         |
|-------------------------------------|-------------------------------------------------------------------------------------------------------------------------|
| Minimum supported client<br/> | None supported<br/>                                                                                               |
| Minimum supported server<br/> | Windows Server 2008<br/>                                                                                          |
| Assembly<br/>                 | <dl> <dt>Microsoft.RightsManagementServices.Admin.dll</dt> </dl> |



## See also

<dl> <dt>

[**AuditReport**](auditreport-object.md)
</dt> </dl>

 

 



