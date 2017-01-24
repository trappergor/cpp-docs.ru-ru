---
title: "Обработка исключений | Microsoft Docs"
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
  - "vc.mfc.macros.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "доступ к данным DAO.NET, исключения"
  - "макросы исключений"
  - "исключения, создающие MFC функции"
  - "исключения, обработка"
  - "макросы, обработка исключений"
  - "MFC - библиотека, исключения"
  - "исключения OLE, функции MFC"
  - "функции завершения, MFC - библиотека"
ms.assetid: 26d4457c-8350-48f5-916e-78f919787c30
caps.latest.revision: 16
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Обработка исключений
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Если программы, несколько анормалных вызываемых условия и ошибок «исключения» могут возникать.  Они могут включать нехватка памяти, ошибки выделения ресурсов и сбоев поиска файлов.  
  
 Библиотеки Microsoft Foundation Class использует схему обработки исключений, которая была смоделирована тесно после одного Комитетом предложенного по стандартам ANSI C для C\+\+.  Обработчик исключений необходимо настроить до вызова функции, которая может столкнуться при возникновении нестандартной ситуации.  Если функция обнаруживает анормальное состояние, она создает исключение и элемент управления передается обработчик исключений.  
  
 Несколько макросов, входящих в состав библиотеки Microsoft Foundation Class настраивают обработчиков исключений.  Несколько других глобальных функций позволяют создавать специализированные исключения и для выполнения программы, соответственно.  Эти макросы и глобальные функции можно разделить на следующие категории.  
  
-   [Макросы исключения](#_mfc_exception_macros) структура, обработчик исключений.  
  
-   [исключения при порождении функции](#_mfc_exception.2d.throwing_functions), создают исключения определенных типов.  
  
-   [Функции завершения](#_mfc_termination_functions), который вызывает завершение работы программы.  
  
 Дополнительные сведения и примеры см. в статье [Исключения](../../mfc/exception-handling-in-mfc.md).  
  
### Макросы исключения  
  
|||  
|-|-|  
|[TRY](../Topic/TRY.md)|Указывает блок кода обработки исключений.|  
|[CATCH](../Topic/CATCH.md)|Указывает блок кода для перехвата исключения из предыдущего блока **TRY**.|  
|[CATCH\_ALL](../Topic/CATCH_ALL.md)|Указывает блок кода для перехвата всех исключений из предыдущего блока **TRY**.|  
|[AND\_CATCH](../Topic/AND_CATCH.md)|Указывает блок кода для перехвата дополнительных типов исключений из предыдущего блока **TRY**.|  
|[AND\_CATCH\_ALL](../Topic/AND_CATCH_ALL.md)|Указывает блок кода для перехвата все другие дополнительные типы исключений, предшествующий в блок **TRY**.|  
|[END\_CATCH](../Topic/END_CATCH.md)|Завершает последние **CATCH** или блок кода `AND_CATCH`.|  
|[END\_CATCH\_ALL](../Topic/END_CATCH_ALL.md)|Завершает последний блок кода `CATCH_ALL`.|  
|[THROW](../Topic/THROW%20\(MFC\).md)|Создает конкретное исключение.|  
|[THROW\_LAST](../Topic/THROW_LAST.md)|Создает в данный момент обработанного исключения следующему внешнему обработчику.|  
  
### Исключения при порождении функции  
  
|||  
|-|-|  
|[AfxThrowArchiveException](../Topic/AfxThrowArchiveException.md)|Создает исключение архива.|  
|[AfxThrowFileException](../Topic/AfxThrowFileException.md)|Создает исключение файла.|  
|[AfxThrowMemoryException](../Topic/AfxThrowMemoryException.md)|Создает исключение памяти.|  
|[AfxThrowNotSupportedException](../Topic/AfxThrowNotSupportedException.md)|Выдает неподдерживаемое исключение.|  
|[AfxThrowResourceException](../Topic/AfxThrowResourceException.md)|Создает исключение, ресурс\-не\- Windows.|  
|[AfxThrowUserException](../Topic/AfxThrowUserException.md)|Создает исключение в действии пользователем начатом программы.|  
  
 MFC предоставляет 2 при порождении исключения функции специально для исключений OLE:  
  
### Функции исключения OLE  
  
|||  
|-|-|  
|[AfxThrowOleDispatchException](../Topic/AfxThrowOleDispatchException.md)|Создает исключение внутри функции ole\-автоматизации.|  
|[AfxThrowOleException](../Topic/AfxThrowOleException.md)|Создает исключение OLE.|  
  
 Для поддержки исключения баз данных классы базы данных предоставляют 2 классы исключений, `CDBException` и `CDaoException` и глобальной функции для поддержки типов исключений.  
  
### Функции исключения DAO  
  
|||  
|-|-|  
|[AfxThrowDAOException](../Topic/AfxThrowDaoException.md)|Создает исключение [CDaoException](../../mfc/reference/cdaoexception-class.md) из собственного кода.|  
|[AfxThrowDBException](../Topic/AfxThrowDBException.md)|Создает исключение [CDBException](../../mfc/reference/cdbexception-class.md) из собственного кода.|  
  
 MFC предоставляет следующие возможности завершения.  
  
### Функции завершения  
  
|||  
|-|-|  
|[AfxAbort](../Topic/AfxAbort.md)|Вызывается при завершении приложения, когда произошла неустранимая ошибка.|  
  
## См. также  
 [Макросы и глобальные объекты](../../mfc/reference/mfc-macros-and-globals.md)   
 [CException Class](../../mfc/reference/cexception-class.md)