---
title: "CException Class | Microsoft Docs"
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
  - "CException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchiveException class, базовый класс"
  - "CDaoException class, базовый класс"
  - "CDBException class, базовый класс"
  - "CException class"
  - "CFileException class, базовый класс"
  - "CInternetException class, базовый класс"
  - "CMemoryException class, базовый класс"
  - "CNotSupportedException class, базовый класс"
  - "COleDispatchException class, базовый класс"
  - "COleException class, базовый класс"
  - "CResourceException class, базовый класс"
  - "CUserException class"
  - "исключения, classes for"
  - "макросы, обработка исключений"
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
caps.latest.revision: 22
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Базовый класс для всех исключений в библиотеки Microsoft Foundation Class.  
  
## Синтаксис  
  
```  
class AFX_NOVTABLE CException : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CException::CException](../Topic/CException::CException.md)|Создает объект `CException`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CException::Delete](../Topic/CException::Delete.md)|Удаляет объект `CException`.|  
|[CException::ReportError](../Topic/CException::ReportError.md)|Информирует сообщение об ошибке в окне сообщения пользователю.|  
  
## Заметки  
 Поскольку `CException` абстрактный базовый класс нельзя создать напрямую, объекты `CException` необходимо создать объекты производных классов.  Если необходимо создать собственное `CException`\- вставка класс стилей, используйте один из производных классов, перечисленных выше, что и у модели.  Убедитесь, что производный класс также используется `IMPLEMENT_DYNAMIC`.  
  
 Производные классы и их описания перечислены ниже:  
  
|||  
|-|-|  
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Базовый класс для ресурс\-критических исключений MFC|  
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Условия исключения несостоятельного довода|  
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение нехватки памяти|  
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Запрос неподдержанной операции|  
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Исключение, характерное для Архив\-|  
|[CFileException](../../mfc/reference/cfileexception-class.md)|Исключение, характерное для Файл\-|  
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Ресурс не найден или не создаваемыми Windows|  
|[COleException](../../mfc/reference/coleexception-class.md)|OLE исключение|  
|[CDBException](../../mfc/reference/cdbexception-class.md)|Исключение базы данных \(то есть условия исключения, вызвавшего классы баз данных MFC на основе ODBC\)|  
|[COleDispatchException](../Topic/COleDispatchException%20Class.md)|Исключение диспетчера \(\) OLE automation|  
|[CUserException](../../mfc/reference/cuserexception-class.md)|Исключение, указывающее, что ресурс не удалось найти|  
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Исключения объекта доступа к данным \(то есть условия исключения, полученные для классов DAO\)|  
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|Исключение Интернета \(то есть условия исключения для классов, поступающие через интернет\).|  
  
 Эти исключения предназначены для использования с макросами [THROW](../Topic/THROW%20\(MFC\).md), [THROW\_LAST](../Topic/THROW_LAST.md), [ПОПЫТКА](../Topic/TRY.md), [CATCH](../Topic/CATCH.md), [AND\_CATCH](../Topic/AND_CATCH.md) и [END\_CATCH](../Topic/END_CATCH.md).  Дополнительные сведения об исключениях см. в разделе [Обработка исключений](../../mfc/reference/exception-processing.md) или в статье [Обработка исключений \(MFC\)](../../mfc/exception-handling-in-mfc.md).  
  
 Чтобы перехватить определенное исключение, используйте соответствующий производный класс.  Для перехвата всех типов исключений, используйте `CException`, а затем используйте [CObject::IsKindOf](../Topic/CObject::IsKindOf.md) чтобы различать между `CException`\- производных классов.  Обратите внимание, что рабочие `CObject::IsKindOf` только для классов, объявленные с макросом [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md), чтобы воспользоваться преимуществами динамической проверки типа.  Любое `CException`\- производный класс, который будет создан должен использовать макрос `IMPLEMENT_DYNAMIC`, слишком.  
  
 Сведения об исключении можно сообщить пользователю путем вызова [GetErrorMessage](../Topic/CFileException::GetErrorMessage.md), 2 или [ReportError](../Topic/CException::ReportError.md) функции\-члена, работают с любым из производных классов `CException`.  
  
 Если исключение перехватывается одним из макросов, то объект `CException` удаление автоматически; не удаляйте его самостоятельно.  Если исключение перехватывается с помощью ключевого слова **catch**, оно автоматически не удалено.  См. статью [Обработка исключений \(MFC\)](../../mfc/exception-handling-in-mfc.md) дополнительные сведения о том, когда удалять объект exeption.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 `CException`  
  
## Требования  
 **Header:**  afx.h  
  
## См. также  
 [CObject Class](../Topic/CObject%20Class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Обработка исключений](../../mfc/reference/exception-processing.md)   
 [Инструкции: Создайте мои собственные пользовательские классы исключений?](http://go.microsoft.com/fwlink/?LinkId=128045)