---
title: "CInternetException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CInternetException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CInternetException class"
  - "обработка исключений, Internet operations"
  - "исключения, Интернет"
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CInternetException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет состояние исключения, относящиеся к операции через интернет.  
  
## Синтаксис  
  
```  
class CInternetException : public CException  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CInternetException::CInternetException](../Topic/CInternetException::CInternetException.md)|Создает объект `CInternetException`.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CInternetException::m\_dwContext](../Topic/CInternetException::m_dwContext.md)|Значение контекста, связанные с операцией, вызвавшей исключение.|  
|[CInternetException::m\_dwError](../Topic/CInternetException::m_dwError.md)|Ошибка, вызвавшая исключение.|  
  
## Заметки  
 Класс `CInternetException` включает 2 открытых элементов данных: он хранит код ошибки, связанный с исключением, а другое содержит идентификатор контекста интернет\-приложения, связанного с ошибкой.  
  
 Дополнительные сведения об идентификаторах контекста для приложений через интернет см. в статье [Устройств, используемые при программировании с WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## Требования  
 **Header:**  afxinet.h  
  
## См. также  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)