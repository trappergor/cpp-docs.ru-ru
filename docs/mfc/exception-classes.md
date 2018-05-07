---
title: Классы исключений | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.classes.exception
dev_langs:
- C++
helpviewer_keywords:
- exception classes [MFC]
- exception handling [MFC], exception classes
- MFC, exceptions
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ce4085d0f5f2dcc73d126d04b7560ef8360ffd9
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="exception-classes"></a>Классы исключений
Библиотека классов предоставляет механизм обработки исключений, на основе класса `CException`. Платформа приложения использует исключений в коде; Кроме того, их можно использовать в указанное имя. Дополнительные сведения см. в статье [исключения](../mfc/exception-handling-in-mfc.md). Можно наследовать собственные типы исключений из `CException`.  
  
 MFC предоставляет класс исключения, от которого необходимо наследовать свои собственные исключения, а также классы исключений для всех исключений, которые он поддерживает.  
  
 [CException](../mfc/reference/cexception-class.md)  
 Базовый класс для исключений.  
  
 [CArchiveException](../mfc/reference/carchiveexception-class.md)  
 Исключение архива.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Исключения, возникающие в результате сбоя в операции базы данных DAO.  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 Исключения, возникающие в результате ошибки во время обработки базы данных ODBC.  
  
 [CFileException](../mfc/reference/cfileexception-class.md)  
 Исключение, ориентированного на файлы.  
  
 [CMemoryException](../mfc/reference/cmemoryexception-class.md)  
 Исключение нехватки памяти.  
  
 [CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)  
 Исключения, возникающие в результате использует неподдерживаемую возможность.  
  
 [COleException](../mfc/reference/coleexception-class.md)  
 Исключения, возникающие в результате ошибки во время обработки OLE. Этот класс используется, контейнеры и серверы.  
  
 [COleDispatchException](../mfc/reference/coledispatchexception-class.md)  
 Исключения, возникающие в результате ошибки во время автоматизации. Автоматизации исключения создаваемые серверы автоматизации и перехвачено клиентами автоматизации.  
  
 [CResourceException](../mfc/reference/cresourceexception-class.md)  
 Исключения, возникающие в результате сбоя загрузки ресурса Windows.  
  
 [CUserException](../mfc/reference/cuserexception-class.md)  
 Исключение, используемое для остановки операции, инициированные пользователем. Как правило пользователь получил уведомление проблемы до этого исключения.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../mfc/class-library-overview.md)

