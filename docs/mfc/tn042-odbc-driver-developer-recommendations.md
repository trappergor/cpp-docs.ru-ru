---
title: TN042. Рекомендации по драйверу ODBC для разработчиков
ms.date: 11/04/2016
f1_keywords:
- vc.odbc
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
ms.openlocfilehash: 67f7a86a247b60be66dabb0a89f04d39ce76222b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372137"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042. Рекомендации по драйверу ODBC для разработчиков

> [!NOTE]
> Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

В этой заметке описаны рекомендации для авторов драйверов ODBC. В нем излагаются общие требования и предположения о функциональности ODBC, которые делают классы базы данных MFC, а также различные ожидаемые семантические детали. Описана обязательная функциональность `CRecordset` драйвера для поддержки трех режимов Open **(только вперед,** **снимок** и **динасет).**

## <a name="odbcs-cursor-library"></a>Библиотека Курзора ODBC

Классы базы данных MFC представляют пользователю функциональность, которая во многих случаях превосходит функциональность, предоставляемую большинством драйверов ODBC уровня 1. К счастью, библиотека Cursor ODBC будет слой себя между классами базы данных и драйвера, и автоматически обеспечит большую часть этой дополнительной функциональности.

Например, большинство драйверов 1.0 не поддерживают обратную прокрутку. Библиотека Cursor может обнаружить это, и будет кэшировать строки от драйвера и представить их по запросу на FETCH_PREV вызовов дюйма `SQLExtendedFetch`

Другим важным примером зависимости библиотеки курсоров является позиционирование обновлений. Большинство драйверов 1.0 также не имеют позиционных обновлений, но библиотека курсоров будет генерировать операторы обновления, которые определяют целевой ряд на источнике данных на основе текущих значений кэшированных данных или кэшированного значения метки времени.

Библиотека классов никогда не использует несколько наборов строк. Таким образом, `SQLSetPos` несколько инструкций всегда применяются к строке 1 строки строки.

## <a name="cdatabases"></a>CDatabases

Каждый `CDatabase` выделяет один **HDBC**. (Если `CDatabase` `ExecuteSQL` функция 'используется, **hSTMT** временно выделяется.) Так что `CDatabase`если несколько 'Ы необходимы, несколько **HDBC**с **henV** должны быть поддержаны.

Классы баз данных требуют библиотеки курсоров. Это отражено в `SQLSetConnections` **вызове SQL_ODBC_CURSORS,** **SQL_CUR_USE_ODBC**.

`SQLDriverConnect`, **SQL_DRIVER_COMPLETE** используется `CDatabase::Open` для установления подключения к источнику данных.

Водитель должен `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >= поддерживать `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >=  **SQL_OAC_LEVEL1,** **SQL_OSC_MINIMUM.**

Для поддержки транзакций `CDatabase` и их зависимых `SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR` записей, а **SQL_CURSOR_ROLLBACK_BEHAVIOR** должны иметь **SQL_CR_PRESERVE.** В противном случае попытки выполнения управления транзакциями будут проигнорированы.

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY`должны быть поддержаны. Если он вернет "Y", операции обновления не будут выполняться на источнике данных.

Если `CDatabase` открывается ReadOnly, попытка установить источник данных читать `SQLSetConnectOption SQL_ACCESS_MODE`только будет сделано с, **SQL_MODE_READ_ONLY**.

Если идентификаторы требуют цитирования, эта `SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR` информация должна быть возвращена от водителя с вызовом.

Для отладки `SQLGetInfo SQL_DBMS_VER` и **SQL_DBMS_NAME** извлекаются из драйвера.

`SQLSetStmtOption SQL_QUERY_TIMEOUT`и **SQL_ASYNC_ENABLE** может быть `CDatabase`вызван на **HDBC**' s .

`SQLError`может быть вызван с любыми или всеми аргументами NULL.

Конечно, `SQLAllocEnv`и `SQLAllocConnect` `SQLDisconnect` `SQLFreeConnect` нужно поддерживать.

## <a name="executesql"></a>ExecuteSQL

В дополнение к выделению и освобождению `ExecuteSQL` `SQLExecDirect`временного `SQLFetch` `SQLNumResultCol` **HSTMT**, звонки , и `SQLMoreResults`. `SQLCancel`может быть вызван на **HSTMT**.

## <a name="getdatabasename"></a>GetDatabaseName

`SQLGetInfo SQL_DATABASE_NAME`будет называться.

## <a name="begintrans-committrans-rollback"></a>BeginTrans, CommitTrans, Откат

`SQLSetConnectOption SQL_AUTOCOMMIT`и, `SQLTransact SQL_COMMIT` **SQL_ROLLBACK** и **SQL_AUTOCOMMIT** будут вызываться, если запросы транзакций сделаны.

## <a name="crecordsets"></a>CRecordsets

`SQLAllocStmt`, `SQLPrepare` `SQLExecute` ( `Open` (Для и `Requery`), `SQLExecDirect` `SQLFreeStmt` (для операций обновления), должны быть поддержаны. `SQLNumResultCols`и `SQLDescribeCol` будут вызваны на результаты, установленные в разное время.

`SQLSetParam`широко используется для связывания данных параметров и **DATA_AT_EXEC** функциональности.

`SQLBindCol`широко используется для регистрации местоположений хранения данных выходной колонки с ODBC.

Для `SQLGetData` извлечения **SQL_LONG_VARCHAR** и **SQL_LONG_VARBINARY** данных используются два вызова. Первый вызов пытается найти общую длину значения `SQLGetData` столбца, позвонив с cbMaxValue 0, но с действительным pcbValue. Если pcbValue удерживает **SQL_NO_TOTAL,** выбрасывается исключение. В противном случае выделяется `SQLGetData` **HGLOBAL** и делается еще один вызов для получения всего результата.

## <a name="updating"></a>Updating

Если запрашивается пессимистическая блокировка, `SQLGetInfo SQL_LOCK_TYPES` будет запрошена. Если **SQL_LCK_EXCLUSIVE** не поддерживается, будет брошено исключение.

Попытки обновить `CRecordset` **(снимок** или **dynaset)** приведет к выделению второго **HSTMT.** Для драйверов, не поддерживающих второй **HSTMT,** библиотека курсоров будет имитировать эту функциональность. К сожалению, иногда это может означать принудительное выполнение текущего запроса по первому **HSTMT** до завершения до обработки второго запроса **HSTMT.**

`SQLFreeStmt SQL_CLOSE`и **SQL_RESET_PARAMS** SQL_RESET_PARAMS `SQLGetCursorName` и будет вызываться во время операций обновления.

Если в **outputColumns**есть **CLongBinarys,** необходимо поддерживать **DATA_AT_EXEC** функциональность ODBC. Это включает в `SQLExecDirect` `SQLParamData` себя `SQLPutData`возвращение **SQL_NEED_DATA** из , и .

`SQLRowCount`называется после выполнения, чтобы убедиться, что только `SQLExecDirect`1 запись была обновлена .

## <a name="forwardonly-cursors"></a>Впередтолько курсоры

Для `SQLFetch` операций `Move` требуется только. Обратите внимание, что **курсоры forwardOnly** не поддерживают обновления.

## <a name="snapshot-cursors"></a>Снимки курсоры

Функциональность моментального снимка требует `SQLExtendedFetch` поддержки. Как отмечалось выше, библиотека курсора ODBC будет `SQLExtendedFetch`обнаруживать, когда водитель не поддерживает, и обеспечит ьму необходимую поддержку сама.

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** должны поддерживать **SQL_SO_STATIC**.

## <a name="dynaset-cursors"></a>Dynaset Курсоры

Ниже приведена минимальная поддержка, необходимая для открытия динасета:

`SQLGetInfo`, **SQL_ODBC_VER** должны вернуться > "01".

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** должны поддерживать **SQL_SO_KEYSET_DRIVEN**.

`SQLGetInfo`, **SQL_ROW_UPDATES** должны вернуть "Y".

`SQLGetInfo`**, SQL_POSITIONED_UPDATES** должны поддерживать **SQL_PS_POSITIONED_DELETE** и **SQL_PS_POSITIONED_UPDATE.**

Кроме того, если запрашивается пессимистическая блокировка, `SQLSetPos` будет сделан звонок с irow 1, fRefresh FALSE и fLock **SQL_LCK_EXCLUSIVE.**

## <a name="see-also"></a>См. также раздел

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические заметки по категориям](../mfc/technical-notes-by-category.md)
