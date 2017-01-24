---
title: "CMemoryException Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMemoryException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "обработка исключений С++, память"
  - "CMemoryException class"
  - "исключения, memory type"
  - "memory exceptions"
  - "память, обработка исключений"
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
caps.latest.revision: 20
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMemoryException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет условия исключения нехватки памяти.  
  
## Синтаксис  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMemoryException::CMemoryException](../Topic/CMemoryException::CMemoryException.md)|Создает объект `CMemoryException`.|  
  
## Заметки  
 Добавочная квалификация не более не требуется или невозможна.  Исключения вызываются автоматически **новый** памяти.  При написании собственные функции памяти с помощью `malloc`, например, ответственные за создание исключения памяти.  
  
 Дополнительные сведения о `CMemoryException` см. в статье [Обработка исключений \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## Требования  
 **Header:**  afx.h  
  
## См. также  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)