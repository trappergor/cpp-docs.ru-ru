---
title: Классы исключений
ms.date: 11/04/2016
f1_keywords:
- vc.classes.exception
helpviewer_keywords:
- exception classes [MFC]
- exception handling [MFC], exception classes
- MFC, exceptions
ms.assetid: 1a2caf12-b3e9-4189-86d2-bf7a595bf025
ms.openlocfilehash: 907b34b12ffdaa70c4377a1012a66662fbba12d0
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619525"
---
# <a name="exception-classes"></a>Классы исключений

Библиотека классов предоставляет механизм обработки исключений на основе класса `CException` . Платформа приложений использует исключения в своем коде; их также можно использовать в. Дополнительные сведения см. в статье [исключения](exception-handling-in-mfc.md). Вы можете создавать собственные типы исключений из `CException` .

MFC предоставляет класс Exception, из которого можно получить собственное исключение, а также классы исключений для всех исключений, которые он поддерживает.

[CException](reference/cexception-class.md)<br/>
Базовый класс для исключений.

[CArchiveException](reference/carchiveexception-class.md)<br/>
Исключение архива.

[CDaoException](reference/cdaoexception-class.md)<br/>
Исключение, полученное в результате сбоя в операции с базой данных DAO.

[CDBException](reference/cdbexception-class.md)<br/>
Исключение, полученное в результате сбоя обработки базы данных ODBC.

[CFileException](reference/cfileexception-class.md)<br/>
Файловый объектно-ориентированное исключение.

[CMemoryException](reference/cmemoryexception-class.md)<br/>
Исключение нехватки памяти.

[CNotSupportedException](reference/cnotsupportedexception-class.md)<br/>
Исключение, полученное при использовании неподдерживаемой функции.

[COleException](reference/coleexception-class.md)<br/>
Исключение, полученное при сбое обработки OLE. Этот класс используется как контейнерами, так и серверами.

[COleDispatchException](reference/coledispatchexception-class.md)<br/>
Исключение, полученное в результате ошибки во время автоматизации. Исключения автоматизации генерируются серверами службы автоматизации и перехватываются клиентами автоматизации.

[CResourceException](reference/cresourceexception-class.md)<br/>
Исключение, полученное при сбое загрузки ресурса Windows.

[CUserException](reference/cuserexception-class.md)<br/>
Исключение, используемое для отмены инициированной пользователем операции. Как правило, пользователь уведомил о проблеме до возникновения этого исключения.

## <a name="see-also"></a>См. также раздел

[Общие сведения о классах](class-library-overview.md)
