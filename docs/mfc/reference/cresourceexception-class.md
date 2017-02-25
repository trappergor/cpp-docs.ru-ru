---
title: "CResourceException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CResourceException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CResourceException class"
  - "исключения, ресурс"
  - "resource allocation exception"
  - "resource exceptions"
  - "ресурсы [C++], выделение"
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CResourceException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Созданный при Windows не может найти или выделения запрошенного ресурса.  
  
## Синтаксис  
  
```  
class CResourceException : public CSimpleException  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CResourceException::CResourceException](../Topic/CResourceException::CResourceException.md)|Создает объект `CResourceException`.|  
  
## Заметки  
 Добавочная квалификация не более не требуется или невозможна.  
  
 Дополнительные сведения об использовании `CResourceException` см. в статье [Обработка исключений \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## Требования  
 **Заголовок:** afxwin.h  
  
## См. также  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)