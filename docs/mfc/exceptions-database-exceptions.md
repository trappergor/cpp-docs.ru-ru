---
title: Исключения. Исключения баз данных
ms.date: 11/04/2016
helpviewer_keywords:
- DAO [MFC], exceptions
- exceptions [MFC], database
- exception handling [MFC], databases
- ODBC exceptions [MFC]
- ODBC [MFC], exceptions
- database exceptions [MFC]
- databases [MFC], exception handling
- error codes [MFC], database exception handling
ms.assetid: 28daf260-f824-4be6-aecc-1f859e6dec26
ms.openlocfilehash: 17a52787462301e839cb2e960fad8b480380ba49
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50492807"
---
# <a name="exceptions-database-exceptions"></a>Исключения. Исключения баз данных

В этой статье объясняется, как обрабатывать исключения базы данных. Большая часть материала в данной статье применяется при работе с классами MFC для Open Database Connectivity (ODBC) или классов MFC для объектов доступа к данным (DAO). Материалы, относящиеся к одной или другой моделью явно помечен. Ниже приведен список разделов.

- [Способы обработки исключений](#_core_approaches_to_exception_handling)

- [Это пример обработки исключений базы данных](#_core_a_database_exception.2d.handling_example)

##  <a name="_core_approaches_to_exception_handling"></a> Способы обработки исключений

Этот подход аналогичен ли вы работаете с DAO или ODBC.

Всегда следует писать обработчики исключений для обработки исключительных условий.

Прагматичный подход к перехвату исключений базы данных является тестирование приложений в сценарии исключений. Определите, скорее всего, исключения, которые могут возникнуть для операции в коде и принудительно к возникновению исключения. Затем изучите выходные данные трассировки, чтобы увидеть, какие исключения, или просмотрите сведения об ошибке в отладчике. Это позволяет узнать, при котором возвращаются коды, вы увидите в сценариях исключения, которую вы используете.

### <a name="error-codes-used-for-odbc-exceptions"></a>Коды ошибок, используемые для ODBC-исключения

Помимо определенных framework коды возврата, которые имеют имена вида **AFX_SQL_ERROR_XXX**, некоторые [CDBExceptions](../mfc/reference/cdbexception-class.md) основаны на [ODBC](../data/odbc/odbc-basics.md) коды возврата. Коды возврата для таких исключений имеют имена вида **SQL_ERROR_XXX**.

Коды возврата, определяемые платформой и определяемые ODBC — что классы баз данных может возвращать, описаны в разделе [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) данными-членом класса `CDBException`. Дополнительные сведения о кодах возврата, определенном ODBC можно найти в пакете SDK ODBC *справочнике программиста* в библиотеке MSDN.

### <a name="error-codes-used-for-dao-exceptions"></a>Коды ошибок, используемые для исключения DAO

Для DAO исключений обычно находится Дополнительные сведения. Сведения об ошибке доступны в трех данные-члены перехваченного [CDaoException](../mfc/reference/cdaoexception-class.md) объекта:

- [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) содержит указатель на [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md) объект, который инкапсулирует сведения об ошибке в DAO коллекция объектов ошибок, связанных с базой данных.

- [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) содержит расширенный код ошибки из классов MFC DAO. Эти коды ошибок, которые имеют имена вида **AFX_DAO_ERROR_XXX**, описаны в элемент данных в `CDaoException`.

- [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) содержит объект OLE **SCODE** из DAO, если применимо. Редко, вам потребуется работать с данным кодом ошибки, тем не менее. Обычно Дополнительные сведения можно найти в другие два элемента данных. Элемент данных для получения дополнительных сведений см. в разделе **SCODE** значения.

Дополнительные сведения об ошибках, тип объекта ошибки DAO и в коллекцию ошибок DAO DAO можно найти в класс [CDaoException](../mfc/reference/cdaoexception-class.md).

##  <a name="_core_a_database_exception.2d.handling_example"></a> Это пример обработки исключений базы данных

Следующий пример осуществляет попытку создать [CRecordset](../mfc/reference/crecordset-class.md)-объект в куче с производной от **новый** оператор, а затем откройте набор записей (для источника данных ODBC). Аналогичный пример для классов DAO см. в разделе «DAO исключение пример» ниже.

### <a name="odbc-exception-example"></a>Пример ODBC-исключение

[Откройте](../mfc/reference/crecordset-class.md#open) функция-член может выдать исключение (типа [CDBException](../mfc/reference/cdbexception-class.md) для классов ODBC), поэтому этот код квадратные скобки `Open` вызов с **попробуйте** блока. Последующие **catch** блок будет перехватывать `CDBException`. Можно проверить исключение сам объект, называется `e`, но в этом случае достаточно знать, что попытка создать набор записей не удалось. **Catch** блок отображает окно сообщения и чистка путем удаления объекта набора записей.

[!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>Пример исключений DAO

DAO пример аналогичен примеру для ODBC, но обычно можно получить дополнительные виды информации. Следующий код также пытается открыть набор записей. Если эта попытка порождает исключение, можно изучить элемент данных объекта исключения, сообщения об ошибках. Как в предыдущем примере ODBC, возможно, будет достаточно знать, что создать набор записей не удалось.

[!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

Этот код получает строку сообщения об ошибке из [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) члена объекта исключения. MFC вводит этот элемент, когда он создает исключение.

Описание сведений об ошибках, возвращаемые `CDaoException` объекта, см. в разделе классы [CDaoException](../mfc/reference/cdaoexception-class.md) и [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md).

При работе с базами данных Microsoft Jet (.mdb) и в большинстве случаев при работе с ODBC, будет существовать только один объект ошибки. В редких случаях, когда вы используете источник данных ODBC и содержит несколько ошибок можно перебирать коллекцию ошибок DAO в зависимости от количества ошибок, возвращаемых [CDaoException::GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount). Вызов каждой проходе через цикл, [CDaoException::GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo) пополнение `m_pErrorInfo` элемент данных.

## <a name="see-also"></a>См. также

[Обработка исключений](../mfc/exception-handling-in-mfc.md)

