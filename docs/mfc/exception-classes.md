---
title: Классы исключений | Документация Майкрософт
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
ms.openlocfilehash: dd666f96ed694b57bf02eb3ad239783828b69e48
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46439267"
---
# <a name="exception-classes"></a>Классы исключений

Библиотека классов предоставляет механизм обработки исключений, на основе класса `CException`. Платформа приложений использует исключения в коде; Кроме того, их можно использовать в вашем. Дополнительные сведения см. в статье [исключения](../mfc/exception-handling-in-mfc.md). Можно создавать производные собственные типы исключений из `CException`.

MFC предоставляет класс исключения, от которого необходимо наследовать свои собственные исключения, а также классы исключений для всех исключений, которые он поддерживает.

[CException](../mfc/reference/cexception-class.md)<br/>
Базовый класс для исключений.

[CArchiveException](../mfc/reference/carchiveexception-class.md)<br/>
Исключение архива.

[CDaoException](../mfc/reference/cdaoexception-class.md)<br/>
Исключение, полученный в результате сбоя в операции базы данных DAO.

[CDBException](../mfc/reference/cdbexception-class.md)<br/>
Исключение, полученный в результате ошибки во время обработки базы данных ODBC.

[CFileException](../mfc/reference/cfileexception-class.md)<br/>
Исключение, ориентированные на файлы.

[CMemoryException](../mfc/reference/cmemoryexception-class.md)<br/>
Исключение out of memory.

[CNotSupportedException](../mfc/reference/cnotsupportedexception-class.md)<br/>
Исключение, полученный в результате использует неподдерживаемую возможность.

[COleException](../mfc/reference/coleexception-class.md)<br/>
Исключение, полученный в результате ошибки во время обработки OLE. Этот класс используется, контейнеры и серверы.

[COleDispatchException](../mfc/reference/coledispatchexception-class.md)<br/>
Исключение, полученный в результате ошибки во время автоматизации. Автоматизации исключения, порождаемые серверы автоматизации и перехватываются клиенты автоматизации.

[CResourceException](../mfc/reference/cresourceexception-class.md)<br/>
Исключение, полученный в результате сбоя загрузки ресурса Windows.

[CUserException](../mfc/reference/cuserexception-class.md)<br/>
Исключение, используемое для остановки операции инициированного пользователем. Как правило пользователь получает уведомление проблему прежде, чем это исключение.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../mfc/class-library-overview.md)

