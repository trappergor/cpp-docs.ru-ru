---
title: "CDBException Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDBException"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDBException class"
  - "database exceptions [C++]"
  - "ошибки [C++], база данных"
  - "exceptions [C++], база данных"
  - "классы ODBC [C++], исключения"
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# CDBException Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Представляет состояние исключения, полученные из классов базы данных.  
  
## Синтаксис  
  
```  
  
class CDBException : public CException  
  
```  
  
## Члены  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CDBException::m\_nRetCode](../Topic/CDBException::m_nRetCode.md)|Содержит код возврата ODBC \(ODBC\) типа **RETCODE**.|  
|[CDBException::m\_strError](../Topic/CDBException::m_strError.md)|Содержит строку, описывающую ошибку в буквенно\-цифровые термины.|  
|[CDBException::m\_strStateNativeOrigin](../Topic/CDBException::m_strStateNativeOrigin.md)|Содержит строку, описывающую ошибку в терминах кодов ошибок, возвращаемых ODBC.|  
  
## Заметки  
 Класс включает 2 открытых членов данных можно использовать для определения причины возникновения исключения или для отображения текста, описывающее исключение.  Объекты `CDBException` встроенные и созданные функции\-членами классов базы данных.  
  
> [!NOTE]
>  Этот класс является одним из классов MFC ODBC \(ODBC\).  Если вместо этого использовать более новые классы DAO \(DAO\), используйте [CDaoException](../../mfc/reference/cdaoexception-class.md).  Все имена классов DAO имеют "CDao" в качестве префикса.  Дополнительные сведения см. в статье [Общие сведения: программирование базы данных](../../data/data-access-programming-mfc-atl.md).  
  
 Исключения случаях аварийного выполнения программы, включая условия за пределами элемента управления в качестве источника данных или ошибки ввода\-вывода сети.  Ошибки, можно ожидать, что увидели в обычном курсе выполнить программу обычно не считаются исключениями.  
  
 Доступ к этим объектам в области выражения **CATCH**.  Можно также создать объекты `CDBException` из собственного кода с функцией `AfxThrowDBException` глобальный.  
  
 Дополнительные сведения об обработке ошибок в целом или об объектах `CDBException` см. в разделе статьи [Обработка исключений \(MFC\)](../../mfc/exception-handling-in-mfc.md) и [исключения: исключения базы данных](../../mfc/exceptions-database-exceptions.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## Требования  
 **Header:**  afxdb.h  
  
## См. также  
 [CException Class](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Class](../Topic/CRecordset%20Class.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)   
 [AfxThrowDBException](../Topic/AfxThrowDBException.md)   
 [CRecordset::Update](../Topic/CRecordset::Update.md)   
 [CRecordset::Delete](../Topic/CRecordset::Delete.md)   
 [CException Class](../../mfc/reference/cexception-class.md)