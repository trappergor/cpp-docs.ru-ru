---
title: Класс CDBException
ms.date: 11/04/2016
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
helpviewer_keywords:
- CDBException [MFC], m_nRetCode
- CDBException [MFC], m_strError
- CDBException [MFC], m_strStateNativeOrigin
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
ms.openlocfilehash: bdfb9bd0b45fd241de4378a2caa19e7dd9f9bdf2
ms.sourcegitcommit: 18d3b1e9cdb4fc3a76f7a650c31994bdbd2bde64
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2019
ms.locfileid: "64877491"
---
# <a name="cdbexception-class"></a>Класс CDBException

Представляет условие исключения, поступающее от классов базы данных.

## <a name="syntax"></a>Синтаксис

```
class CDBException : public CException
```

## <a name="members"></a>Участники

### <a name="public-data-members"></a>Открытые члены данных

|name|Описание|
|----------|-----------------|
|[CDBException::m_nRetCode](#m_nretcode)|Содержит код возврата Open Database Connectivity (ODBC), типа RETCODE.|
|[CDBException::m_strError](#m_strerror)|Содержит строку с описанием ошибки в терминах буквенно-цифровых.|
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|Содержит строку, описывающую ошибку с точки зрения коды ошибок, возвращенный ODBC.|

## <a name="remarks"></a>Примечания

Этот класс включает два общих данных члена, которые можно использовать для определения причины исключения или текстовое сообщение, описывающее исключение. `CDBException` объекты конструирования и вызванных функций-членов классов базы данных.

> [!NOTE]
>  Этот класс является одним из классов MFC Open Database Connectivity (ODBC). Если вместо этого вы используете более новые классы объектов доступа к данным (DAO), используйте [CDaoException](../../mfc/reference/cdaoexception-class.md) вместо этого. Все имена классов DAO имеют «CDao» как префикс. Дополнительные сведения см. в статье [Обзор: Программирование баз данных](../../data/data-access-programming-mfc-atl.md).

Исключения случаях аномальных выполнения, включающих условия за пределами элемента управления программы, такие как источник данных или сетевых операций ввода-вывода ошибок. Ошибки, которые могут ожидать см. в ходе нормального выполнения программы, обычно не считаются исключения.

Эти объекты в пределах доступны **CATCH** выражение. Также может породить `CDBException` объектов из кода с помощью `AfxThrowDBException` глобальной функции.

Дополнительные сведения об обработке исключений в общие или о `CDBException` объектов, см. в статьях [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключения: Базы данных исключений](../../mfc/exceptions-database-exceptions.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CDBException`

## <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

##  <a name="m_nretcode"></a>  CDBException::m_nRetCode

Содержит код ошибки ODBC типа RETCODE, возвращенный программирования функции API-интерфейса ODBC приложения.

### <a name="remarks"></a>Примечания

Этот тип включает коды SQL с префиксом, определенном ODBC и коды AFX_SQL с префиксом, определенные классами баз данных. Для `CDBException`, этот элемент будет содержать одно из следующих значений:

- AFX_SQL_ERROR_API_CONFORMANCE драйвер для `CDatabase::OpenEx` или `CDatabase::Open` вызова не соответствует необходимый уровень соответствия API ODBC 1 (SQL_OAC_LEVEL1).

- Не удалось AFX_SQL_ERROR_CONNECT_FAIL соединение с источником данных. Вы передали значение NULL`CDatabase` указатель на ваш конструктор набора записей и повторная попытка создать подключение на основе `GetDefaultConnect` не удалось.

- AFX_SQL_ERROR_DATA_TRUNCATED вы запросили больше данных, чем вы предоставили хранилище для. Сведения о хранилище данных для увеличения `CString` или `CByteArray` типов данных, см. в разделе `nMaxLength` аргумент для [RFX_Text](record-field-exchange-functions.md#rfx_text) и [RFX_Binary](record-field-exchange-functions.md#rfx_binary) в разделе «макросы и Глобальные параметры.»

- Вызов AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED A `CRecordset::Open` запрос подмножества не удалось. Динамических подмножеств данных не поддерживаются драйвером.

- AFX_SQL_ERROR_EMPTY_COLUMN_LIST была предпринята попытка открыть таблицу (или вы присвоили не может быть идентифицирован как вызов процедуры или **ВЫБЕРИТЕ** инструкции), но нет столбцов, определенных в вызовах функций полями записей (RFX) exchange в ваш `DoFieldExchange` переопределить.

- AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH тип RFX работать в вашей `DoFieldExchange` переопределение не совместим с типом данных столбца в наборе записей.

- AFX_SQL_ERROR_ILLEGAL_MODE Вы вызвали `CRecordset::Update` без вызова ранее `CRecordset::AddNew` или `CRecordset::Edit`.

- Не удалось выполнить AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED ваш запрос на блокировку записи для обновления, так как драйвер ODBC не поддерживает блокировку.

- AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED Вы вызвали `CRecordset::Update` или `Delete` для таблицы с уникальным ключом и изменить несколько записей.

- AFX_SQL_ERROR_NO_CURRENT_RECORD предпринята попытка изменить или удалить ранее запись. Вам нужно прокручивать экран новой текущей записи после удаления.

- AFX_SQL_ERROR_NO_POSITIONED_UPDATES, которые не удалось выполнить ваш запрос на подмножества, так как драйвер ODBC не поддерживает позиционированные обновления.

- AFX_SQL_ERROR_NO_ROWS_AFFECTED Вы вызвали `CRecordset::Update` или `Delete`, но во время начала операции записи больше не найден.

- AFX_SQL_ERROR_ODBC_LOAD_FAILED попытка загрузки ODBC. Не удалось; Windows не удалось найти или не удалось загрузить эту библиотеку DLL. Эта ошибка является неустранимой.

- AFX_SQL_ERROR_ODBC_V2_REQUIRED, которые не удалось выполнить ваш запрос на подмножества, так как требуется драйвером ODBC уровня 2-совместимым.

- AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY попытка прокрутки не выполнена, поскольку источник данных не поддерживает обратной прокрутки.

- Вызов AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED A `CRecordset::Open` запросе моментального снимка не удалось. Моментальные снимки не поддерживаются драйвером. (Это должно происходить только при ODBCCURS библиотеки курсоров ODBC. Библиотека DLL отсутствует.)

- AFX_SQL_ERROR_SQL_CONFORMANCE драйвер для `CDatabase::OpenEx` или `CDatabase::Open` вызова не соответствует необходимый уровень соответствия SQL ODBC «Минимум» (SQL_OSC_MINIMUM).

- Драйвер AFX_SQL_ERROR_SQL_NO_TOTAL ODBC не удалось задать общий размер `CLongBinary` значение данных. Поскольку блок глобальной памяти может не быть предварительно, возможно, сбой операции.

- AFX_SQL_ERROR_RECORDSET_READONLY вы пытались изменить набор только для чтения, или источник данных доступен только для чтения. Операции обновления не могут быть выполнены с набором записей или `CDatabase` объекта, связанного с ним.

- Сбой функции SQL_ERROR. Сообщение об ошибке, возвращаемый функцией ODBC `SQLError` хранится в `m_strError` элемент данных.

- Функция SQL_INVALID_HANDLE сбой из-за недопустимый дескриптор дескриптора соединения и дескриптора инструкции. Это указывает на программную ошибку. Дополнительные сведения недоступны из функции ODBC `SQLError`.

Коды с префиксом SQL определяются ODBC. Коды с префиксом AFX определены в файле AFXDB. H, найден в MFC\INCLUDE.

##  <a name="m_strerror"></a>  CDBException::m_strError

Содержит строку с описанием ошибки, вызвавшей исключение.

### <a name="remarks"></a>Примечания

Строка описывает ошибку в терминах буквенно-цифровых. Более подробные сведения и пример, см. в разделе `m_strStateNativeOrigin`.

##  <a name="m_strstatenativeorigin"></a>  CDBException::m_strStateNativeOrigin

Содержит строку с описанием ошибки, вызвавшей исключение.

### <a name="remarks"></a>Примечания

Строка имеет форму «состояние: % s, машинный код: % ld, источник: % s», где коды формата, в порядке, будут заменены значениями, которые описывают:

- SQLSTATE, заканчивающуюся нулем строку, содержащее код ошибки пяти символов, возвращаемых в *szSqlState* параметра функции ODBC `SQLError`. В приложении А перечислены значения SQLSTATE [коды ошибок ODBC](/sql/odbc/reference/appendixes/appendix-a-odbc-error-codes)в *Справочник по программированию ODBC*. Пример «S0022».

- Машинный код ошибки, относящиеся к источнику данных, возвращаемых в *pfNativeError* параметр `SQLError` функции. Пример 207.

- Текст сообщения об ошибке возвращаются в *szErrorMsg* параметр `SQLError` функции. Это сообщение состоит из нескольких имен в квадратных скобках. Как ошибка передается от источника для пользователя, каждый компонент "ODBC" (источник данных, драйвер, диспетчер драйверов) добавляет собственное имя. Эта информация поможет найти источник ошибки. Пример: [Microsoft] [ODBC SQL Server Driver] [SQL Server]

Платформа framework интерпретирует строку ошибки и помещает его компоненты в `m_strStateNativeOrigin`; Если `m_strStateNativeOrigin` содержит сведения для более чем одна ошибка, ошибки разделяются символы новой строки. Платформа помещает текст ошибки буквенно-цифровых в `m_strError`.

Дополнительные сведения о кодах, используемых для этой строки, см. в разделе [SQLError](/sql/odbc/reference/syntax/sqlerror-function) работать в *Справочник по программированию ODBC*.

### <a name="example"></a>Пример

Из ODBC. «Состояние: S0022, машинный код: 207, источник:\[Майкрософт]\[драйвер ODBC SQL Server]\[SQL Server] Недопустимый столбец «ColName»»

В `m_strStateNativeOrigin`: «Состояние: S0022, машинный код: 207, источник:\[Майкрософт]\[драйвер ODBC для SQL Server]\[SQL Server]»

В `m_strError`: «Недопустимое имя столбца «ColName»»

## <a name="see-also"></a>См. также

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Класс CRecordset](../../mfc/reference/crecordset-class.md)<br/>
[Класс CFieldExchange](../../mfc/reference/cfieldexchange-class.md)<br/>
[CRecordset::Update](../../mfc/reference/crecordset-class.md#update)<br/>
[CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)<br/>
[Класс CException](../../mfc/reference/cexception-class.md)
