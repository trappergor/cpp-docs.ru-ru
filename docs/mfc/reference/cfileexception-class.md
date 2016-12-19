---
title: "CFileException Class | Microsoft Docs"
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
  - "CFileException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFile class, exceptions of"
  - "CFileException class"
  - "исключения, file type"
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
caps.latest.revision: 20
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFileException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет состояние исключения, связанного с файлом.  
  
## Синтаксис  
  
```  
class CFileException : public CException  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileException::CFileException](../Topic/CFileException::CFileException.md)|Создает объект `CFileException`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileException::ErrnoToException](../Topic/CFileException::ErrnoToException.md)|Код причины возвращений, соответствующее номеру ошибки во время выполнения.|  
|[CFileException::GetErrorMessage](../Topic/CFileException::GetErrorMessage.md)|Получает сообщение, описывающее исключение.|  
|[CFileException::OsErrorToException](../Topic/CFileException::OsErrorToException.md)|Возвращает код причины, соответствующего коду ошибки операционной системы.|  
|[CFileException::ThrowErrno](../Topic/CFileException::ThrowErrno.md)|Выдает исключение файла на основе номер ошибки времени выполнения.|  
|[CFileException::ThrowOsError](../Topic/CFileException::ThrowOsError.md)|Выдает исключение файла на основе номер ошибки операционной системы.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CFileException::m\_cause](../Topic/CFileException::m_cause.md)|Содержит переносимый код, соответствующий причине исключения.|  
|[CFileException::m\_lOsError](../Topic/CFileException::m_lOsError.md)|Содержит связанный номер ошибки операционной системы.|  
|[CFileException::m\_strFileName](../Topic/CFileException::m_strFileName.md)|Содержит имя файла для этого исключения.|  
  
## Заметки  
 Класс `CFileException` содержит открытые элементы данных, которые содержат переносимый причину и код ошибки работать\-система\- номер конкретного.  Класс также предоставляет статические функции\-члены для генерирования исключений файла и возвращение кодов причины как ошибки операционной системы, так и для ошибок во время выполнения c.  
  
 Объекты `CFileException` встроенные и созданные в функции\-члены `CFile` и в функции\-члены производных классов.  Доступ к этим объектам в области выражения **CATCH**.  При переносимости, используйте только код причины для получения причину исключения.  Дополнительные сведения об исключениях см. в статье [Обработка исключений \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## Требования  
 **Header:**  afx.h  
  
## См. также  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Обработка исключений](../../mfc/reference/exception-processing.md)