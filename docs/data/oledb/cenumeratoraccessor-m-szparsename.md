---
title: "CEnumeratorAccessor::m_szParseName | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CEnumeratorAccessor::m_szParseName"
  - "ATL::CEnumeratorAccessor::m_szParseName"
  - "m_szParseName"
  - "CEnumeratorAccessor.m_szParseName"
  - "ATL.CEnumeratorAccessor.m_szParseName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_szParseName"
ms.assetid: 32e826b6-0890-4db4-aa92-fc1ea3f528b2
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CEnumeratorAccessor::m_szParseName
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Строка, которую требуется передать [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) для получения моникер для источника данных или перечислителя.  
  
## Синтаксис  
  
```  
  
WCHAR m_szParseName[129];  
  
```  
  
## Заметки  
 В разделе [ISourcesRowset::GetSourcesRowset](https://msdn.microsoft.com/en-us/library/ms711200.aspx) справочника *программиста OLE DB* дополнительные сведения.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CEnumeratorAccessor](../../data/oledb/cenumeratoraccessor-class.md)