---
title: "CDaoException Class | Microsoft Docs"
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
  - "CDaoException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoException class"
  - "коллекции, ошибки DAO"
  - "доступ к данным DAO.NET, исключения"
  - "ошибки [C++], DAO"
  - "Errors collection, DAO"
  - "исключения, in MFC DAO classes"
ms.assetid: b2b01fa9-7ce2-42a1-842e-40f13dc50da4
caps.latest.revision: 24
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет состояние исключения, полученные из классов баз данных MFC на основе объектов доступа к данным \(DAO\).  
  
## Синтаксис  
  
```  
class CDaoException : public CException  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoException::CDaoException](../Topic/CDaoException::CDaoException.md)|Создает объект `CDaoException`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoException::GetErrorCount](../Topic/CDaoException::GetErrorCount.md)|Возвращает число ошибок в коллекции ошибок компонента database engine.|  
|[CDaoException::GetErrorInfo](../Topic/CDaoException::GetErrorInfo.md)|Сведения об ошибке возвращений о конкретном объекте ошибки в коллекцию ошибок.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDaoException::m\_nAfxDaoError](../Topic/CDaoException::m_nAfxDaoError.md)|Содержит расширенный код ошибки для любой ошибки в классах MFC DAO.|  
|[CDaoException::m\_pErrorInfo](../Topic/CDaoException::m_pErrorInfo.md)|Указатель на объект [CDaoErrorInfo](../../mfc/reference/cdaoerrorinfo-structure.md), который содержит сведения об одном объекте ошибки DAO.|  
|[CDaoException::m\_scode](../Topic/CDaoException::m_scode.md)|Значение [SCODE](../Topic/CDaoException::m_scode.md), связанное с ошибкой.|  
  
## Заметки  
 Класс содержит открытые элементы данных можно использовать для определения причины исключения.  Объекты `CDaoException` встроенные и созданные функции\-членами классов базы данных DAO.  
  
> [!NOTE]
>  Классы баз данных DAO MFC отличаются от классов баз данных на основе ODBC \(ODBC\).  Все имена классов базы данных DAO имеют префикс "CDao".  Можно получить доступ к источнику данных ODBC с помощью классов DAO.  В общем случае классы MFC DAO способны на основе более чем классы MFC на основе ODBC; DAO\- на основе классы могут получить доступ к данным, включая через драйвер ODBC через собственный компонент database engine.  DAO\- на основе классов также поддерживают операции языка описания данных DDL \(язык DDL\), такие как добавление таблицы с помощью классов DAO непосредственно, без вызова.  Дополнительные сведения об исключениях, создаваемых классов ODBC см. в разделе [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Можно получить доступ к объектам исключения в области выражения [CATCH](../Topic/CATCH.md).  Можно также создать объекты `CDaoException` из собственного кода с функцией [AfxThrowDaoException](../Topic/AfxThrowDaoException.md) глобальный.  
  
 В MFC DAO записываются все ошибки в виде исключений, типа `CDaoException`.  Если перехватывать исключение этого типа можно использовать функции\-члены `CDaoException` чтобы получить сведения из всех объектов ошибок DAO, хранящихся в коллекции ошибок компонента database engine.  По мере приближения происходит ошибка, один или несколько объектов ошибки помещаются в коллекцию ошибок.  \(Обычно коллекции содержится только один объект ошибки; если используется источник данных ODBC, которые с наибольшей вероятностью будут получать объекты нескольких ошибок\). Если другая операция DAO формирует ошибку, коллекция ошибок очищена, а новый объект ошибки помещается в коллекцию ошибок.  Операции DAO, которые не создают ошибок не влияет на коллекцию ошибок.  
  
 Для кодов ошибок DAO см. в разделе файл DAOERR.H.  Дополнительные сведения см. в разделе "доступ к данным Перехватываемые ошибки" в Справке DAO.  
  
 Дополнительные сведения об обработке ошибок в целом или об объектах `CDaoException` см. в разделе статьи [Обработка исключений \(MFC\)](../../mfc/exception-handling-in-mfc.md) и [исключения: исключения базы данных](../../mfc/exceptions-database-exceptions.md).  Вторая статья содержит пример кода, который демонстрирует обработку ошибок в DAO.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDaoException`  
  
## Требования  
 **Header:**  afxdao.h  
  
## См. также  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CException Class](../../mfc/reference/cexception-class.md)