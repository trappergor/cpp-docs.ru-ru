---
title: "CSimpleException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSimpleException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleException class"
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# CSimpleException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс является базовым классом для ресурс\- критических исключений MFC.  
  
## Синтаксис  
  
```  
  
class AFX_NOVTABLE CSimpleException : public CException  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleException::CSimpleException](../Topic/CSimpleException::CSimpleException.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CSimpleException::GetErrorMessage](../Topic/CSimpleException::GetErrorMessage.md)|Содержит текст об ошибке, которая возникла.|  
  
## Заметки  
 `CSimpleException` базовый класс для ресурс\- критических исключений MFC и обрабатывает владельца и инициализацию сообщения об ошибке.  Следующие классы используют `CSimpleException` в качестве своего базового класса:  
  
|||  
|-|-|  
|[Класс CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение нехватки памяти|  
|[Класс CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Запросы для неподдержанной операции|  
|[Класс CResourceException](../../mfc/reference/cresourceexception-class.md)|Ресурс не найден или не создаваемыми Windows|  
|[Класс CUserException](../../mfc/reference/cuserexception-class.md)|Исключение, указывающее ресурс не удалось найдено|  
|[Класс CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Исключение, указывающее на недопустимый аргумент|  
  
 Поскольку `CSimpleException` абстрактный базовый класс нельзя объявить объект `CSimpleException` напрямую.  Вместо этого необходимо объявить производные объекты, что и в предыдущей таблице.  При объявлении собственный производный класс, используйте предыдущие классы, как модель.  
  
 Дополнительные сведения см. в разделе [класс CException](../../mfc/reference/cexception-class.md) и [Обработка исключений \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## Требования  
 **Header:** afx.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Обработка исключений](../../mfc/exception-handling-in-mfc.md)