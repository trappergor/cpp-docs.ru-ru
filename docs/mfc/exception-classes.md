---
title: "Классы исключений | Microsoft Docs"
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
  - "vc.classes.exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "классы исключений"
  - "обработка исключений, классы исключений"
  - "MFC - библиотека, исключения"
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы исключений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Библиотека классов предоставляет механизм обработки исключений, основанный на классе `CException`.  Платформа приложения использует исключения в своем коде; их также можно использовать в твоих.  Дополнительные сведения см. в статье [Исключения](../mfc/exception-handling-in-mfc.md).  Можно создавать производные собственные типы исключений в `CException`.  
  
 MFC предоставляет классы исключений, из которого можно создать собственные исключение, так и классы исключений для всех исключений он поддерживает.  
  
 [CException](../mfc/reference/cexception-class.md)  
 Базовый класс для исключений.  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 Исключение архива.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Исключение и в результате сбоя в операции базы данных DAO.  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 Исключение и в результате сбоя на обработку базы данных ODBC.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 Ориентирована на файл исключение.  
  
 [CMemoryException](../mfc/reference/cmemoryexception-class.md)  
 Исключение нехватки памяти.  
  
 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)  
 Исключение и в результате использования неподдерживаемой возможности.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Исключение и в результате сбоя в OLE обработки.  Этот класс используется как контейнерами, и серверами.  
  
 [COleDispatchException](../Topic/COleDispatchException%20Class.md)  
 Исключение, что приводит к возникновению ошибки во время автоматизации.  Исключения автоматизации исключений перехватываются автоматизации серверами и клиентами автоматизации.  
  
 [CResourceException](../mfc/reference/cresourceexception-class.md)  
 Исключение и в результате сбоя загрузить ресурс Windows.  
  
 [CUserException](../mfc/reference/cuserexception-class.md)  
 Исключение, используемое для остановки инициируемую пользователем операции.  Обычно пользователь получает уведомление проблемы, прежде чем это исключение.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)