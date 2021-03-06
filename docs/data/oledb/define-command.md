---
title: "DEFINE_COMMAND | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.technology: ["cpp-data"]
ms.topic: "reference"
f1_keywords: ["DEFINE_COMMAND"]
dev_langs: ["C++"]
helpviewer_keywords: ["DEFINE_COMMAND macro"]
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
author: "mikeblome"
ms.author: "mblome"
ms.workload: ["cplusplus", "data-storage"]
---
# DEFINE_COMMAND
Specifies the command that will be used to create the rowset when using the [CCommand](../../data/oledb/ccommand-class.md) class. Accepts only string types matching the specified application type (ANSI or Unicode).  
  
> [!NOTE]
>  It is recommended that you use [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) instead of `DEFINE_COMMAND`.  
  
## Syntax  
  
```cpp
DEFINE_COMMAND(x, szCommand)  
  
```  
  
#### Parameters  
 *x*  
 [in] The name of the user record (command) class.  
  
 `szCommand`  
 [in] The command string that will be used to create the rowset when using [CCommand](../../data/oledb/ccommand-class.md).  
  
## Remarks  
 The command string that you specify will be used as the default if you do not specify command text in the [CCommand::Open](../../data/oledb/ccommand-open.md) method.  
  
 This macro accepts ANSI strings if you build your application as ANSI, or Unicode strings if you build your application as Unicode. It is recommended that you use [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) instead of `DEFINE_COMMAND`, because the former accepts Unicode strings, regardless of the ANSI or Unicode application type.  
  
## Example  
 See [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## Requirements  
 **Header:** atldbcli.h  
  
## See Also  
 [Macros and Global Functions for OLE DB Consumer Templates](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)