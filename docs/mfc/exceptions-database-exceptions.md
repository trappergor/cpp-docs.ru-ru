---
title: Исключения. Исключения баз данных
ms.date: 09/17/2019
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
ms.openlocfilehash: 894960338a7e8c293054ade00e0cdf3295648bb7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81366626"
---
# <a name="exceptions-database-exceptions"></a>Исключения. Исключения баз данных

В этой статье объясняется, как обрабатывать исключения баз данных. Большая часть материала в этой статье применяется независимо от того, работаете ли вы с классами MFC для open Database Connectivity (ODBC) или с классами MFC для объектов доступа к данным (DAO). Материал, специфичный для той или иной модели, явно обозначен. Будут рассмотрены следующие задачи:

- [Подходы к обработке исключений](#_core_approaches_to_exception_handling)

- [Пример обработки исключений базы данных](#_core_a_database_exception.2d.handling_example)

## <a name="approaches-to-exception-handling"></a><a name="_core_approaches_to_exception_handling"></a>Подходы к обработке исключений

Этот подход одинитак, работаете ли вы с DAO (устаревшим) или ODBC.

Для обработки исключительных условий всегда следует писать обработчики исключений.

Наиболее прагматичный подход к ловле исключений баз данных — это тестирование приложения с помощью сценариев исключения. Определите вероятные исключения, которые могут возникнуть для операции в коде, и заставит произойти исключение. Затем изучите вывод трассировки, чтобы узнать, какое исключение выбрасывается, или изучите возвращенную информацию об ошибке в отладчике. Это позволяет узнать, какие коды возврата вы увидите для сценариев исключений, которые вы используете.

### <a name="error-codes-used-for-odbc-exceptions"></a>Коды ошибок, используемые для исключений ODBC

В дополнение к коды возврата, определенные инфраструктурой, которые имеют названия формы **AFX_SQL_ERROR_XXX,** некоторые [CDBExceptions](../mfc/reference/cdbexception-class.md) основаны на кодах возврата [ODBC.](../data/odbc/odbc-basics.md) Коды возврата для таких исключений имеют названия формы **SQL_ERROR_XXX**.

Коды возврата — как определяемые платформой, так и определяемые с помощью ODBC, которые могут возвращать классы базы данных, задокументированы в элементе данных [m_nRetCode](../mfc/reference/cdbexception-class.md#m_nretcode) класса `CDBException`. Дополнительная информация о кодах возврата, определенных ODBC, доступна в *справочнике программиста* ODBC SDK в библиотеке MSDN.

### <a name="error-codes-used-for-dao-exceptions"></a>Коды ошибок, используемые для исключений DAO

Для исключений DAO, как правило, доступна дополнительная информация. Вы можете получить доступ к информации об ошибках через трех членов данных пойманного объекта [CDaoException:](../mfc/reference/cdaoexception-class.md)

- [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) содержит указатель на объект [CDaoErrorInfo,](../mfc/reference/cdaoerrorinfo-structure.md) который инкапсулирует информацию об ошибках в коллекции объектов ошибок DAO, связанных с базой данных.

- [m_nAfxDaoError](../mfc/reference/cdaoexception-class.md#m_nafxdaoerror) содержит расширенный код ошибки из классов MFC DAO. Эти коды ошибок, которые имеют имена формы **AFX_DAO_ERROR_XXX,** `CDaoException`задокументированы в соответствии с данными в .

- [m_scode](../mfc/reference/cdaoexception-class.md#m_scode) содержит OLE **SCODE** от DAO, если это применимо. Однако редко вам придется работать с этим кодом ошибки. Обычно более подробная информация доступна в двух других членов данных. Подробнее о значениях SCODE можно узнать о значении **SCODE.**

Дополнительная информация об ошибках DAO, типе объекта ошибки DAO и сборе ошибок DAO доступна под классом [CDaoException.](../mfc/reference/cdaoexception-class.md)

## <a name="a-database-exception-handling-example"></a><a name="_core_a_database_exception.2d.handling_example"></a>Пример исключения базы данных

Следующий пример пытается построить [CRecordset-производный](../mfc/reference/crecordset-class.md)объект на куче с **новым** оператором, а затем открыть набор записей (для источника данных ODBC). Для аналогичного примера для классов DAO см.

### <a name="odbc-exception-example"></a>Пример исключения ODBC

Функция [Open](../mfc/reference/crecordset-class.md#open) member может выбросить исключение (типа [CDBException](../mfc/reference/cdbexception-class.md) для классов ODBC), поэтому этот код заковеливает `Open` вызов блоком **попытки.** Последующий блок **улова** поймает `CDBException`. Вы можете изучить сам `e`объект исключения, называемый, но в этом случае достаточно знать, что попытка создания набора записей не удалась. Блок **catch** отображает окно сообщений и очищается путем удаляния объекта записи.

[!code-cpp[NVC_MFCDatabase#36](../mfc/codesnippet/cpp/exceptions-database-exceptions_1.cpp)]

### <a name="dao-exception-example"></a>Пример исключения DAO

Пример DAO аналогичен примеру ODBC, но обычно можно получить больше видов информации. Следующий код также пытается открыть набор записей. Если эта попытка выбрасывает исключение, можно изучить элемент данных объекта исключения для получения информации об ошибке. Как и в предыдущем примере ODBC, вероятно, достаточно знать, что попытка создания уровня записей провалилась.

[!code-cpp[NVC_MFCDatabase#37](../mfc/codesnippet/cpp/exceptions-database-exceptions_2.cpp)]

Этот код получает строку сообщения об ошибке от [m_pErrorInfo](../mfc/reference/cdaoexception-class.md#m_perrorinfo) члена объекта исключения. MFC заполняет этот член, когда он бросает исключение.

Для обсуждения информации об ошибке, возвращенной объектом, `CDaoException` [CDaoErrorInfo](../mfc/reference/cdaoerrorinfo-structure.md)см. [CDaoException](../mfc/reference/cdaoexception-class.md)

При работе с базами данных Microsoft Jet (.mdb) и в большинстве случаев, когда вы работаете с ODBC, будет только один объект ошибки. В тех редких случаях, когда вы используете источник данных ODBC и есть несколько ошибок, вы можете цикл через сбор ошибок DAO на основе количества ошибок, возвращенных [CDaoException::GetErrorCount](../mfc/reference/cdaoexception-class.md#geterrorcount). Каждый раз, когда через цикл, вызов [CDaoException::GetErrorInfo](../mfc/reference/cdaoexception-class.md#geterrorinfo) пополнить данный `m_pErrorInfo` член.

## <a name="see-also"></a>См. также раздел

[Обработка исключений](../mfc/exception-handling-in-mfc.md)
