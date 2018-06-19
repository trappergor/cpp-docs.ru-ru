---
title: 'TN042: Рекомендации для разработчиков драйвера ODBC | Документы Microsoft'
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
ms.openlocfilehash: 35c75f5c5bae3a1b56abe91340de00f373663792
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33384798"
---
# <a name="tn042-odbc-driver-developer-recommendations"></a>TN042. Рекомендации по драйверу ODBC для разработчиков
> [!NOTE]
>  Следующее техническое примечание не было обновлено, поскольку сначала оно было включено в электронную документацию. В результате некоторые процедуры и разделы могут быть устаревшими или неверными. Для получения последних сведений рекомендуется выполнить поиск интересующей темы в алфавитном указателе документации в Интернете.  
  
 Эта заметка описывает правила для модулей записи драйвера ODBC. В нем изложены общие требования и предположения функции ODBC, классы баз данных MFC и различных ожидаемый семантические сведения. Необходимые функциональные возможности драйвера для поддержки трех `CRecordset` открыть режимы (**forwardOnly**, **моментального снимка** и **динамический набор**) описаны.  
  
## <a name="odbcs-cursor-library"></a>Библиотека курсоров ODBC  
 Классы баз данных MFC функциональные возможности предлагать пользователю, во многих случаях превосходит функциональные возможности, предоставляемые большинство драйверы ODBC уровня 1. К счастью библиотека курсоров ODBC расположить себя от классов базы данных и драйвера и автоматически предоставят большую часть дополнительные функциональные возможности.  
  
 Например большинство 1.0 драйверы не поддерживают обратной прокрутки. Библиотека курсоров можно обнаружить и будет кэшировать строки с помощью драйвера и представит запросили FETCH_PREV вызовы в **SQLExtendedFetch**.  
  
 Еще один пример важные зависимость от библиотеки курсоров — позиционированные обновления. Большинство 1.0 драйверы также не имеют позиционированные обновления, но библиотеку курсоров будет создавать инструкции update, которые идентифицируют целевой строки в источнике данных, на основе его текущего значения кэшированных данных, или значение отметки времени кэширования.  
  
 Библиотека классов никогда не используются несколько наборов строк. Таким образом, некоторые **SQLSetPos** всегда применяются инструкции по строке 1 набора строк.  
  
## <a name="cdatabases"></a>CDatabases  
 Каждый `CDatabase` выделяет один **HDBC**. (Если `CDatabase` `ExecuteSQL` используется функция, **HSTMT** временно выделена.) Таким образом, если несколько `CDatabase`необходимы, несколько **HDBC**с в каждом **HENV** должно поддерживаться.  
  
 Классы баз данных требуется библиотека курсоров. Это отражено в **SQLSetConnections** вызвать **SQL_ODBC_CURSORS**, **SQL_CUR_USE_ODBC**.  
  
 **SQLDriverConnect**, **SQL_DRIVER_COMPLETE** используется `CDatabase::Open` для установления соединения с источником данных.  
  
 Драйвер должен поддерживать **SQLGetInfo SQL_ODBC_API_CONFORMANCE** >= **SQL_OAC_LEVEL1**, **SQLGetInfo SQL_ODBC_SQL_CONFORMANCE**  >=  **SQL_OSC_MINIMUM**.  
  
 В порядке для транзакций, которые должны поддерживаться `CDatabase` и его зависимые наборы записей **SQLGetInfo SQL_CURSOR_COMMIT_BEHAVIOR** и **SQL_CURSOR_ROLLBACK_BEHAVIOR** должен иметь **SQL_CR_PRESERVE**. В противном случае попытки выполнить операции управления будет игнорироваться.  
  
 **SQLGetInfo SQL_DATA_SOURCE_READ_ONLY** должно поддерживаться. Если он возвращает «Y», никакие операции обновления выполняется в источнике данных.  
  
 Если `CDatabase` открыт только для чтения, попытка задать чтение источника данных будет выполняться только с **SQLSetConnectOption SQL_ACCESS_MODE**, **SQL_MODE_READ_ONLY**.  
  
 Если идентификаторы требуют заключения в кавычки, эти сведения будут возвращены из драйвера с **SQLGetInfo SQL_IDENTIFIER_QUOTE_CHAR** вызова.  
  
 Для отладки, **SQLGetInfo SQL_DBMS_VER** и **SQL_DBMS_NAME** извлекаются из драйвера.  
  
 **SQLSetStmtOption SQL_QUERY_TIMEOUT** и **SQL_ASYNC_ENABLE** может быть вызван для `CDatabase` **HDBC**.  
  
 **SQLError** может быть вызвана с любой или все аргументы значение NULL.  
  
 Конечно **SQLAllocEnv**, **SQLAllocConnect**, **SQLDisconnect** и **SQLFreeConnect** должно поддерживаться.  
  
## <a name="executesql"></a>ExecuteSQL  
 Помимо выделения и освобождения временного **HSTMT**, `ExecuteSQL` вызовы **SQLExecDirect**, **SQLFetch**, **SQLNumResultCol**и `SQLMoreResults`. **SQLCancel** может быть вызван для **HSTMT**.  
  
## <a name="getdatabasename"></a>GetDatabaseName  
 **SQLGetInfo SQL_DATABASE_NAME** будет вызван.  
  
## <a name="begintrans-committrans-rollback"></a>Откат BeginTrans CommitTrans,  
 **SQLSetConnectOption SQL_AUTOCOMMIT** и **параметром SQL_COMMIT SQLTransact**, **SQL_ROLLBACK** и **SQL_AUTOCOMMIT** будет вызываться, если транзакция запрашивает выполняются.  
  
## <a name="crecordsets"></a>CRecordsets  
 **SQLAllocStmt**, **SQLPrepare**, **SQLExecute** (для **откройте** и **Requery**), **SQLExecDirect**  (для операций обновления), **SQLFreeStmt** должно поддерживаться. **SQLNumResultCols** и **SQLDescribeCol** будет вызван для результирующего набора в различные моменты времени.  
  
 **SQLSetParam** широко используется для привязки данных параметра и **DATA_AT_EXEC** функциональные возможности.  
  
 **SQLBindCol** широко используется для регистрации вывода места хранения данных столбца с ODBC.  
  
 Два **SQLGetData** вызовы используются для получения **SQL_LONG_VARCHAR** и **SQL_LONG_VARBINARY** данных. Первый вызов пытается найти общая длина значений столбца, путем вызова **SQLGetData** cbMaxValue 0, но с допустимым pcbValue. Если содержит pcbValue **SQL_NO_TOTAL**, создается исключение. В противном случае `HGLOBAL` выделяется, а другой **SQLGetData** вызов для получения всех результатов.  
  
## <a name="updating"></a>Updating  
 Если запрашивается Пессимистическая блокировка **SQLGetInfo SQL_LOCK_TYPES** будет направлен запрос. Если **SQL_LCK_EXCLUSIVE** — не поддерживается, будет создано исключение.  
  
 Пытается обновить `CRecordset` (**моментального снимка** или **динамический набор**) приведет к второй **HSTMT** для распределения. Драйверы, которые не поддерживают второй **HSTMT**, библиотека курсоров имитирует эту функциональность. К сожалению, это иногда означает принудительное текущего запроса на первом **HSTMT** до завершения перед обработкой второй **HSTMT**запроса.  
  
 **SQLFreeStmt SQL_CLOSE** и **SQL_RESET_PARAMS** и **SQLGetCursorName** будет вызываться во время операции обновления.  
  
 При наличии **CLongBinarys** в **outputColumns**, ODBC **DATA_AT_EXEC** функциональные возможности, которые должны поддерживаться. Сюда входят возврат **SQL_NEED_DATA** из **SQLExecDirect**, **SQLParamData** и **SQLPutData**.  
  
 **SQLRowCount** вызывается после выполнения для проверки, что только 1 запись была обновлена с **SQLExecDirect**.  
  
## <a name="forwardonly-cursors"></a>ForwardOnly курсоров  
 Только **SQLFetch** является обязательным для **переместить** операций. Обратите внимание, что **forwardOnly** курсоры не поддерживают обновление.  
  
## <a name="snapshot-cursors"></a>Курсоры моментального снимка  
 Возможности создания моментальных снимков требуется **SQLExtendedFetch** поддержки. Как указано выше, библиотека курсоров ODBC будет обнаружить, когда драйвер не поддерживает **SQLExtendedFetch**и обеспечивают необходимую поддержку сам.  
  
 **SQLGetInfo**, **SQL_SCROLL_OPTIONS** должен поддерживать **SQL_SO_STATIC**.  
  
## <a name="dynaset-cursors"></a>Динамический набор курсоров  
 Ниже приведен Минимальное несущее множество, необходимо открыть динамический набор.  
  
 **SQLGetInfo**, **SQL_ODBC_VER** должен возвращать > «01».  
  
 **SQLGetInfo**, **SQL_SCROLL_OPTIONS** должен поддерживать **SQL_SO_KEYSET_DRIVEN**.  
  
 **SQLGetInfo**, **SQL_ROW_UPDATES** должен возвращать «Y».  
  
 **SQLGetInfo**, **SQL_POSITIONED_UPDATES** должен поддерживать **SQL_PS_POSITIONED_DELETE** и **SQL_PS_POSITIONED_UPDATE**.  
  
 Кроме того, если запрашивается пессимистичных блокировок вызов **SQLSetPos** irow 1, fRefresh FALSE и fLock **SQL_LCK_EXCLUSIVE** будут внесены.  
  
## <a name="see-also"></a>См. также  
 [Технические примечания по номеру](../mfc/technical-notes-by-number.md)   
 [Технические примечания по категории](../mfc/technical-notes-by-category.md)

