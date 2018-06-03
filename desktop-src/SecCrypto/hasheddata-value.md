---
Description: Retrieves the hashed data after successful calls to the Hash method.
ms.assetid: 02ba92d2-38eb-4c01-99b9-11676e7d49ff
title: HashedData.Value property
ms.technology: desktop
ms.prod: windows
ms.author: windowssdkdev
ms.topic: article
ms.date: 05/31/2018
---

# HashedData.Value property

\[CAPICOM is a 32-bit only component that is available for use in the following operating systems: Windows Server 2008, Windows Vista, and Windows XP. Instead, use the [**HashAlgorithm Class**](https://www.bing.com/search?q=**HashAlgorithm Class**) in the [**System.Security.Cryptography**](https://www.bing.com/search?q=**System.Security.Cryptography**) namespace.\]

The **Value** property retrieves the hashed data after successful calls to the [**Hash**](hasheddata-hash.md) method. The hash value is returned in hexadecimal format. This is the default property.

## Syntax


```VB
HashedData.Value As String
```



## Property value

A string that contains the hashed data in hexadecimal format.

## Remarks

To create the hash of a large amount of data, call the [**Hash**](hasheddata-hash.md) method for each piece of data. The hash of each piece of data is concatenated to the **Value** property until the property is read. The contents of the **Value** property are reset when the property is read.

## Requirements



|                                  |                                                                                        |
|----------------------------------|----------------------------------------------------------------------------------------|
| End of client support<br/> | Windows Vista<br/>                                                               |
| End of server support<br/> | Windows Server 2008<br/>                                                         |
| Redistributable<br/>       | CAPICOM 2.0 or later on Windows Server 2003 and Windows XP<br/>                  |
| DLL<br/>                   | <dl> <dt>Capicom.dll</dt> </dl> |



## See also

<dl> <dt>

[**HashedData**](hasheddata.md)
</dt> </dl>

 

 



