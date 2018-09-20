---
title: 'TN042: Рекомендации по драйверу ODBC разработчиков | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- vc.odbc
dev_langs:
- C++
helpviewer_keywords:
- ODBC drivers [MFC], writing
- databases [MFC], ODBC
- TN042
ms.assetid: ecc6b5d9-f480-4582-9e22-8309fe561dad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 87e31fa0884adc78d3f1026afc59dd0b46ac7602
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375259"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042. Рекомендации по драйверу ODBC для разработчиков

> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.

Эта заметка описывает правила для модулей записи драйвера ODBC. Здесь указаны общие требования и предположения функции ODBC, классы MFC баз данных и различных ожидаемый семантические сведения. Необходимые функциональные возможности драйвера для поддержки трех `CRecordset` открыть режимы (**forwardOnly**, **моментального снимка** и **динамический набор**) описаны.

## <a name="odbcs-cursor-library"></a>Библиотека курсоров ODBC

Классы баз данных MFC представлять функциональные возможности для пользователя, который во многих случаях превосходит функциональных возможностях, предоставляемых большинство драйверов ODBC уровня 1. К счастью библиотека курсоров ODBC расположить себя между классы баз данных и драйвера и автоматически предоставит большую часть этой дополнительной функциональностью.

Например большинство драйверов 1.0 не поддерживают обратной прокрутки. Библиотека курсоров можно обнаружить и будет кэшировать строки из драйвера и представить их по запросу на вызовы FETCH_PREV в `SQLExtendedFetch`.

Другим важным примером зависимость от библиотеки курсоров является позиционированные обновления. Большинство 1.0 драйверы также не имеют позиционированные обновления, но библиотека курсоров будет генерировать операторы update, которые идентифицируют целевой строки в источнике данных, на основе его текущего значения кэшированных данных, или значение метки времени кэширования.

Библиотека классов никогда не используется несколько наборов строк. Таким образом, некоторые `SQLSetPos` операторы всегда применяются к строке 1 набора строк.

## <a name="cdatabases"></a>CDatabases

Каждый `CDatabase` выделяет один **HDBC**. (Если `CDatabase` `ExecuteSQL` используется функция, **HSTMT** временно выделяется.) Таким образом, если несколько `CDatabase`необходимы, несколько **HDBC**s на **HENV** должно поддерживаться.

Классы баз данных требуется библиотека курсоров. Это отражено в `SQLSetConnections` вызвать **SQL_ODBC_CURSORS**, **SQL_CUR_USE_ODBC**.

`SQLDriverConnect`, **SQL_DRIVER_COMPLETE** используется `CDatabase::Open` для установления соединения с источником данных.

Драйвер должен поддерживать `SQLGetInfo SQL_ODBC_API_CONFORMANCE`  >=  **SQL_OAC_LEVEL1**, `SQLGetInfo SQL_ODBC_SQL_CONFORMANCE`  >=  **SQL_OSC_MINIMUM**.

В порядке для транзакций, которые должны поддерживаться для `CDatabase` и его зависимые наборы `SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR` и **SQL_CURSOR_ROLLBACK_BEHAVIOR** должен иметь **SQL_CR_PRESERVE**. В противном случае попытки выполнить операции управления будут игнорироваться.

`SQLGetInfo SQL_DATA_SOURCE_READ_ONLY` должно поддерживаться. Если он возвращает «Y», будут выполняться никакие операции обновления в источнике данных.

Если `CDatabase` открыт только для чтения, попытка задать чтение источника данных будет выполняться только с `SQLSetConnectOption SQL_ACCESS_MODE`, **SQL_MODE_READ_ONLY**.

Если идентификаторы требуют заключения в кавычки, эти сведения будут возвращены из драйвера с `SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR` вызова.

Для отладки, `SQLGetInfo SQL_DBMS_VER` и **SQL_DBMS_NAME** извлекаются из драйвера.

`SQLSetStmtOption SQL_QUERY_TIMEOUT` и **SQL_ASYNC_ENABLE** в может вызываться `CDatabase` **HDBC**.

`SQLError` может вызываться с аргументами any или all значение NULL.

Само собой `SQLAllocEnv`, `SQLAllocConnect`, `SQLDisconnect` и `SQLFreeConnect` должно поддерживаться.

## <a name="executesql"></a>ExecuteSQL

Помимо выделения и освобождения временного **HSTMT**, `ExecuteSQL` вызовы `SQLExecDirect`, `SQLFetch`, `SQLNumResultCol` и `SQLMoreResults`. `SQLCancel` может быть вызван на **HSTMT**.

## <a name="getdatabasename"></a>GetDatabaseName

`SQLGetInfo SQL_DATABASE_NAME` будет вызван.

## <a name="begintrans-committrans-rollback"></a>Примеры BeginTrans, CommitTrans, отката

`SQLSetConnectOption SQL_AUTOCOMMIT` и `SQLTransact SQL_COMMIT`, **SQL_ROLLBACK** и **SQL_AUTOCOMMIT** будет вызываться при запросе транзакции.

## <a name="crecordsets"></a>CRecordsets

`SQLAllocStmt`, `SQLPrepare`, `SQLExecute` (Для `Open` и `Requery`), `SQLExecDirect` (для операций обновления), `SQLFreeStmt` должно поддерживаться. `SQLNumResultCols` и `SQLDescribeCol` будет вызван для результирующего набора в разные моменты времени.

`SQLSetParam` широко используется для привязки данных параметра и **DATA_AT_EXEC** функциональные возможности.

`SQLBindCol` широко используется для регистрации выходных данных расположения для хранения данных столбца с помощью ODBC.

Два `SQLGetData` вызовы используются для получения **SQL_LONG_VARCHAR** и **SQL_LONG_VARBINARY** данных. Первый вызов пытается найти общую длину значения столбца путем вызова `SQLGetData` cbMaxValue 0, но с допустимым pcbValue. Если содержит pcbValue **SQL_NO_TOTAL**, создается исключение. В противном случае **HGLOBAL** выделяется и другой `SQLGetData` вызов для получения всех результатов.

## <a name="updating"></a>Updating

Если запрашивается пессимистической блокировки, `SQLGetInfo SQL_LOCK_TYPES` будет направлен запрос. Если **SQL_LCK_EXCLUSIVE** — не поддерживается, будет создано исключение.

Пытается обновить `CRecordset` (**моментального снимка** или **динамический набор**) приведет к секунды **HSTMT** для распределения. Драйверы, которые не поддерживают второй **HSTMT**, библиотека курсоров имитируется эту функцию. К сожалению, это иногда означает принудительное текущего запроса на первом **HSTMT** до завершения перед обработкой второй **HSTMT**запроса пользователя.

`SQLFreeStmt SQL_CLOSE` и **SQL_RESET_PARAMS** и `SQLGetCursorName` будет вызываться во время операций обновления.

При наличии **CLongBinarys** в **outputColumns**, ODBC **DATA_AT_EXEC** функции должны поддерживаться. Сюда входят возвращение **SQL_NEED_DATA** из `SQLExecDirect`, `SQLParamData` и `SQLPutData`.

`SQLRowCount` вызывается после выполнения, чтобы убедиться, что всего 1 запись была обновлена с `SQLExecDirect`.

## <a name="forwardonly-cursors"></a>ForwardOnly курсоров

Только `SQLFetch` необходим для `Move` операций. Обратите внимание, что **forwardOnly** курсоры не поддерживают обновление.

## <a name="snapshot-cursors"></a>Курсоры моментального снимка

Возможности создания моментальных снимков требуется `SQLExtendedFetch` поддержки. Как отмечалось выше, библиотека курсоров ODBC будет обнаружить, когда драйвер не поддерживает `SQLExtendedFetch`и предоставить необходимую поддержку сам.

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** должен поддерживать **SQL_SO_STATIC**.

## <a name="dynaset-cursors"></a>Курсоры динамических подмножеств данных

Ниже приведен минимальную поддержку, необходимый для открытия динамическим подмножеством данных.

`SQLGetInfo`, **SQL_ODBC_VER** должен возвращать > «01».

`SQLGetInfo`, **SQL_SCROLL_OPTIONS** должен поддерживать **SQL_SO_KEYSET_DRIVEN**.

`SQLGetInfo`, **SQL_ROW_UPDATES** должен возвращать «Y».

`SQLGetInfo`, **SQL_POSITIONED_UPDATES** должен поддерживать **SQL_PS_POSITIONED_DELETE** и **SQL_PS_POSITIONED_UPDATE**.

Кроме того, если запрашивается пессимистической блокировки вызов `SQLSetPos` irow 1, fRefresh FALSE и fLock **SQL_LCK_EXCLUSIVE** будут внесены.

## <a name="see-also"></a>См. также

[Технические примечания по номеру](../mfc/technical-notes-by-number.md)<br/>
[Технические примечания по категории](../mfc/technical-notes-by-category.md)

