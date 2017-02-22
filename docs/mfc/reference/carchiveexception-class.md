---
title: "CArchiveException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CArchiveException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "archive exceptions [C++]"
  - "CArchiveException class"
  - "exceptions [C++], archive"
  - "exceptions [C++], сериализация"
  - "сериализация [C++], исключения"
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CArchiveException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет условия исключения сериализации  
  
## Синтаксис  
  
```  
class CArchiveException : public CException  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CArchiveException::CArchiveException](../Topic/CArchiveException::CArchiveException.md)|Создает объект `CArchiveException`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CArchiveException::m\_cause](../Topic/CArchiveException::m_cause.md)|Указывает причину исключения.|  
|[CArchiveException::m\_strFileName](../Topic/CArchiveException::m_strFileName.md)|Задает имя файла для данного условия исключения.|  
  
## Заметки  
 Класс `CArchiveException` включает общий член данных, который указывает причину исключения.  
  
 Создаются объекты, создаваемые `CArchiveException` и внутренние функции\-члены [CArchive](../../mfc/reference/carchive-class.md).  Доступ к этим объектам в области выражения **CATCH**.  Код причины не зависит от операционной системы.  Дополнительные сведения об исключении см. в разделе [Обработка исключений \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CArchiveException`  
  
## Требования  
 **Header:**  afx.h  
  
## См. также  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CArchive Class](../../mfc/reference/carchive-class.md)   
 [AfxThrowArchiveException](../Topic/AfxThrowArchiveException.md)   
 [Обработка исключений](../../mfc/reference/exception-processing.md)