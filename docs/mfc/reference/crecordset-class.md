---
title: Класс CRecordset
ms.date: 11/04/2016
f1_keywords:
- CRecordset
- AFXDB/CRecordset
- AFXDB/CRecordset::CRecordset
- AFXDB/CRecordset::AddNew
- AFXDB/CRecordset::CanAppend
- AFXDB/CRecordset::CanBookmark
- AFXDB/CRecordset::Cancel
- AFXDB/CRecordset::CancelUpdate
- AFXDB/CRecordset::CanRestart
- AFXDB/CRecordset::CanScroll
- AFXDB/CRecordset::CanTransact
- AFXDB/CRecordset::CanUpdate
- AFXDB/CRecordset::CheckRowsetError
- AFXDB/CRecordset::Close
- AFXDB/CRecordset::Delete
- AFXDB/CRecordset::DoBulkFieldExchange
- AFXDB/CRecordset::DoFieldExchange
- AFXDB/CRecordset::Edit
- AFXDB/CRecordset::FlushResultSet
- AFXDB/CRecordset::GetBookmark
- AFXDB/CRecordset::GetDefaultConnect
- AFXDB/CRecordset::GetDefaultSQL
- AFXDB/CRecordset::GetFieldValue
- AFXDB/CRecordset::GetODBCFieldCount
- AFXDB/CRecordset::GetODBCFieldInfo
- AFXDB/CRecordset::GetRecordCount
- AFXDB/CRecordset::GetRowsetSize
- AFXDB/CRecordset::GetRowsFetched
- AFXDB/CRecordset::GetRowStatus
- AFXDB/CRecordset::GetSQL
- AFXDB/CRecordset::GetStatus
- AFXDB/CRecordset::GetTableName
- AFXDB/CRecordset::IsBOF
- AFXDB/CRecordset::IsDeleted
- AFXDB/CRecordset::IsEOF
- AFXDB/CRecordset::IsFieldDirty
- AFXDB/CRecordset::IsFieldNull
- AFXDB/CRecordset::IsFieldNullable
- AFXDB/CRecordset::IsOpen
- AFXDB/CRecordset::Move
- AFXDB/CRecordset::MoveFirst
- AFXDB/CRecordset::MoveLast
- AFXDB/CRecordset::MoveNext
- AFXDB/CRecordset::MovePrev
- AFXDB/CRecordset::OnSetOptions
- AFXDB/CRecordset::OnSetUpdateOptions
- AFXDB/CRecordset::Open
- AFXDB/CRecordset::RefreshRowset
- AFXDB/CRecordset::Requery
- AFXDB/CRecordset::SetAbsolutePosition
- AFXDB/CRecordset::SetBookmark
- AFXDB/CRecordset::SetFieldDirty
- AFXDB/CRecordset::SetFieldNull
- AFXDB/CRecordset::SetLockingMode
- AFXDB/CRecordset::SetParamNull
- AFXDB/CRecordset::SetRowsetCursorPosition
- AFXDB/CRecordset::SetRowsetSize
- AFXDB/CRecordset::Update
- AFXDB/CRecordset::m_hstmt
- AFXDB/CRecordset::m_nFields
- AFXDB/CRecordset::m_nParams
- AFXDB/CRecordset::m_pDatabase
- AFXDB/CRecordset::m_strFilter
- AFXDB/CRecordset::m_strSort
helpviewer_keywords:
- CRecordset [MFC], CRecordset
- CRecordset [MFC], AddNew
- CRecordset [MFC], CanAppend
- CRecordset [MFC], CanBookmark
- CRecordset [MFC], Cancel
- CRecordset [MFC], CancelUpdate
- CRecordset [MFC], CanRestart
- CRecordset [MFC], CanScroll
- CRecordset [MFC], CanTransact
- CRecordset [MFC], CanUpdate
- CRecordset [MFC], CheckRowsetError
- CRecordset [MFC], Close
- CRecordset [MFC], Delete
- CRecordset [MFC], DoBulkFieldExchange
- CRecordset [MFC], DoFieldExchange
- CRecordset [MFC], Edit
- CRecordset [MFC], FlushResultSet
- CRecordset [MFC], GetBookmark
- CRecordset [MFC], GetDefaultConnect
- CRecordset [MFC], GetDefaultSQL
- CRecordset [MFC], GetFieldValue
- CRecordset [MFC], GetODBCFieldCount
- CRecordset [MFC], GetODBCFieldInfo
- CRecordset [MFC], GetRecordCount
- CRecordset [MFC], GetRowsetSize
- CRecordset [MFC], GetRowsFetched
- CRecordset [MFC], GetRowStatus
- CRecordset [MFC], GetSQL
- CRecordset [MFC], GetStatus
- CRecordset [MFC], GetTableName
- CRecordset [MFC], IsBOF
- CRecordset [MFC], IsDeleted
- CRecordset [MFC], IsEOF
- CRecordset [MFC], IsFieldDirty
- CRecordset [MFC], IsFieldNull
- CRecordset [MFC], IsFieldNullable
- CRecordset [MFC], IsOpen
- CRecordset [MFC], Move
- CRecordset [MFC], MoveFirst
- CRecordset [MFC], MoveLast
- CRecordset [MFC], MoveNext
- CRecordset [MFC], MovePrev
- CRecordset [MFC], OnSetOptions
- CRecordset [MFC], OnSetUpdateOptions
- CRecordset [MFC], Open
- CRecordset [MFC], RefreshRowset
- CRecordset [MFC], Requery
- CRecordset [MFC], SetAbsolutePosition
- CRecordset [MFC], SetBookmark
- CRecordset [MFC], SetFieldDirty
- CRecordset [MFC], SetFieldNull
- CRecordset [MFC], SetLockingMode
- CRecordset [MFC], SetParamNull
- CRecordset [MFC], SetRowsetCursorPosition
- CRecordset [MFC], SetRowsetSize
- CRecordset [MFC], Update
- CRecordset [MFC], m_hstmt
- CRecordset [MFC], m_nFields
- CRecordset [MFC], m_nParams
- CRecordset [MFC], m_pDatabase
- CRecordset [MFC], m_strFilter
- CRecordset [MFC], m_strSort
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
ms.openlocfilehash: 264c9eda4860dfbe41d40c9b454ec40a1a274ba5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368366"
---
# <a name="crecordset-class"></a>Класс CRecordset

Представляет набор записей, выбранных из источника данных.

## <a name="syntax"></a>Синтаксис

```
class CRecordset : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CRecordset::CRecordset](#crecordset)|Формирует объект `CRecordset`. Ваш производный класс должен предоставить конструктор, который вызывает этот.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRecordset::AddNew](#addnew)|Готовится к добавлению новой записи. Позвоните `Update` для завершения добавления.|
|[CRecordset::CanAppend](#canappend)|Возвращает ненулевой, если новые записи `AddNew` могут быть добавлены к набору записей через функцию члена.|
|[CRecordset::CanBookmark](#canbookmark)|Возвращает ненулевой, если запись поддерживает закладки.|
|[CRecordset::Отмена](#cancel)|Отменяет асинхронную операцию или процесс из второго потока.|
|[CRecordset::CancelUpdate](#cancelupdate)|Отменяет любые ожидающие `AddNew` `Edit` обновления из-за операции или операции.|
|[CRecordset::CanRestart](#canrestart)|Возвращает ненулевой, если `Requery` можно вызвать для повторного выполнения запроса записи.|
|[CRecordset::CanScroll](#canscroll)|Возвращает ненулевой, если вы можете прокрутить записи.|
|[CRecordset::CanTransact](#cantransact)|Возвращает ненулевой, если источник данных поддерживает транзакции.|
|[CRecordset::CanUpdate](#canupdate)|Возвращает ненулевой, если запись может быть обновлена (вы можете добавить, обновить или удалить записи).|
|[CRecordset::CheckRowsetОшибка](#checkrowseterror)|Вызывается для обработки ошибок, генерируемых во время записи извлечения.|
|[CRecordset::Закрыть](#close)|Закрывает рекорд и ODBC HSTMT связанные с ним.|
|[CRecordset::Delete](#delete)|Удаляет текущую запись из набора записей. После удаления необходимо явно прокрутить другую запись.|
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|Вызывается для обмена объемными строками данных от источника данных до уровня записи. Реализует объемную биржу месторождений (Bulk RFX).|
|[CRecordset::DoFieldExchange](#dofieldexchange)|Вызывается для обмена данными (в обоих направлениях) между полевыми данными членов регистрации и соответствующей записью об источнике данных. Реализует обмен рекордными полями (RFX).|
|[CRecordset::Edit](#edit)|Подготовитесь к изменениям в текущей записи. Вызов `Update` для завершения досачения.|
|[CRecordset::FlushResultSet](#flushresultset)|Возвращает ненулевой, если есть другой набор результатов, которые необходимо получить, при использовании заданного запроса.|
|[CRecordset::GetBookmark](#getbookmark)|Присваивает значение закладки записи объекту параметра.|
|[CRecordset::GetDefaultConnect](#getdefaultconnect)|Вызывается, чтобы получить строку соединения по умолчанию.|
|[CRecordset::GetDefaultS'L](#getdefaultsql)|Вызывается, чтобы получить строку по умолчанию S'L для выполнения.|
|[CRecordset::GetFieldValue](#getfieldvalue)|Возвращает значение поля в рекорде.|
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|Возвращает количество полей в рекорде.|
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|Возвращает определенные виды информации о полях в наборе записей.|
|[CRecordset::GetRecordCount](#getrecordcount)|Возвращает количество записей в рекорде.|
|[CRecordset::GetRowsetSize](#getrowsetsize)|Возвращает количество записей, которые вы хотите получить во время одного получения.|
|[CRecordset::GetRowsFetched](#getrowsfetched)|Возвращает фактическое количество строк, извлеченных во время получения.|
|[CRecordset::GetRowStatus](#getrowstatus)|Возвращает состояние строки после получения.|
|[CRecordset::GetS'L](#getsql)|Получает строку S'L, используемую для выбора записей для рекорда.|
|[CRecordset::GetStatus](#getstatus)|Получает статус рекорда: индекс текущего рекорда и получен ли окончательный подсчет записей.|
|[CRecordset::GetTableName](#gettablename)|Получает название таблицы, на которой основан рекорд.|
|[CRecordset::IsBOF](#isbof)|Возвращает ненулевой, если рекорд был расположен до первой записи. Отсутствует текущая запись.|
|[CRecordset::Isdeleted](#isdeleted)|Возвращает ненулевой, если запись расположена на удаленной записи.|
|[CRecordset::IsEOF](#iseof)|Возвращает ненулевой, если рекорд был расположен после последней записи. Отсутствует текущая запись.|
|[CRecordset::IsfieldDirty](#isfielddirty)|Возвращает ненулевой, если указанное поле в текущей записи было изменено.|
|[CRecordset::IsFieldNull](#isfieldnull)|Возвращает ненулевой, если указанное поле в текущей записи является нулевым (не имеет значения).|
|[CRecordset::IsfieldNullable](#isfieldnullable)|Возвращает ненулевой, если указанное поле в текущем отчете может быть установлено недействительным (не имеет значения).|
|[CRecordset::IsOpen](#isopen)|Возвращает ненулевой, если `Open` он был вызван ранее.|
|[CRecordset::Перемещение](#move)|Позиции рекорда до определенного количества записей из текущего записи в любом направлении.|
|[CRecordset::MoveFirst](#movefirst)|Позиции текущего рекорда на первом рекорде в рекорде. Тест `IsBOF` для первого.|
|[CRecordset::MoveLast](#movelast)|Позиции текущего записи на последней записи или на последнем наборе строк. Тест `IsEOF` для первого.|
|[CRecordset::MoveNext](#movenext)|Позиции текущей записи на следующей записи или на следующем строке. Тест `IsEOF` для первого.|
|[CRecordset::MovePrev](#moveprev)|Позиции текущего рекорда на предыдущем рекорде или на предыдущем наборе строк. Тест `IsBOF` для первого.|
|[CRecordset::OnsetOptions](#onsetoptions)|Вызывается для набора параметров (используется при выборе) для указанной выписки ODBC.|
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|Вызывается для установки параметров (используется в обновлении) для указанной выписки ODBC.|
|[CRecordset::Открыто](#open)|Открывает запись, извлекая таблицу или выполняя запрос, который представляет собой набор записей.|
|[CRecordset::RefreshRowset](#refreshrowset)|Обновляет данные и состояние указанной строки (ы).|
|[CRecordset::Requery](#requery)|Запускает запрос recordset снова для обновления выбранных записей.|
|[CRecordset::SetAbsolutePosition](#setabsoluteposition)|Позиции рекорда на рекорде, соответствующие указанному рекордному числу.|
|[CRecordset::SetBookmark](#setbookmark)|Позиции рекорда на запись, указанную закладкой.|
|[CRecordset::SetFieldDirty](#setfielddirty)|Отметки указанного поля в текущем отчете изменены.|
|[CRecordset::SetFieldNull](#setfieldnull)|Устанавливает значение указанного поля в текущем отчете как нулевые (не имеющие значения).|
|[CRecordset::SetLockingMode](#setlockingmode)|Устанавливает режим блокировки на «оптимистический» блокировку (по умолчанию) или «пессимистическую» блокировку. Определяет, как записи запираются для обновления.|
|[CRecordset::SetParamNull](#setparamnull)|Устанавливает указанный параметр на нулевую (не имеющая значения).|
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|Позиции курсора на указанном ряду в пределах строки.|
|[CRecordset::SetRowsetSize](#setrowsetsize)|Упоняет количество записей, которые вы хотите получить во время получения.|
|[CRecordset::Обновление](#update)|Завершает или `AddNew` `Edit` выполняет операцию, сохраняя новые или отредактированные данные в источнике данных.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CRecordset::m_hstmt](#m_hstmt)|Содержит ручку оператора оператора ODBC для набора записей. Введите `HSTMT`.|
|[CRecordset::m_nFields](#m_nfields)|Содержит количество полевых данных в записи. Введите `UINT`.|
|[CRecordset::m_nParams](#m_nparams)|Содержит количество параметров данных членов в записи. Введите `UINT`.|
|[CRecordset::m_pDatabase](#m_pdatabase)|Содержит указатель на `CDatabase` объект, через который запись подключена к источнику данных.|
|[CRecordset::m_strFilter](#m_strfilter)|Содержит `CString` пункт, описавающее положение о структурированном языке запросов (S'L). `WHERE` Используется в качестве фильтра для выбора только тех записей, которые отвечают определенным критериям.|
|[CRecordset::m_strSort](#m_strsort)|Содержит `CString` пункт, оговариваемый `ORDER BY` оговорку S'L. Используется для контроля способов сортировки записей.|

## <a name="remarks"></a><a name="remarks"></a>. Замечания

Известные как "записи", `CRecordset` объекты обычно используются в двух формах: динасеты и снимки. Dynaset остается синхронизированным с обновлениями данных, сделанными другими пользователями. Снимок — это статический вид данных. Каждая форма представляет собой набор записей, зафиксированных на момент открытия набора записей, но при прокрутке записи в динассете она отражает изменения, впоследствии внесенные в запись, либо другими пользователями, либо другими записями в вашем приложении.

> [!NOTE]
> Если вы работаете с классами объектов доступа к данным (DAO), а не с классами Open Database Connectivity (ODBC), используйте класс [CDaoRecordset.](../../mfc/reference/cdaorecordset-class.md) Для получения дополнительной информации смотрите статью [Обзор: Программирование базы данных](../../data/data-access-programming-mfc-atl.md).

Для работы с любым видом записи, как правило, `CRecordset`вы получаете класс записей, специфичный для приложений, из . Записи выбирают записи из источника данных, и вы можете:

- Прокрутите записи.

- Обновите записи и укажите режим блокировки.

- Фильтр установить рекорд, чтобы ограничить, какие записи он выбирает из тех, которые доступны на источнике данных.

- Сортировать рекорд.

- Параметризировать рекорд, чтобы настроить его выбор с информацией, не известно до времени выполнения.

Чтобы использовать свой класс, откройте базу данных и создайте объект, `CDatabase` передав конструктору указатель на объект. Затем позвоните в `Open` функцию члена записи, где можно указать, является ли объект динасетом или моментальным снимком. Вызов `Open` выбирает данные из источника данных. После открытия объекта записи используйте его функции членов и членов данных для прокрутки записей и работы над ними. Доступные операции зависят от того, является ли объект динасетом или моментальным снимком, является ли он updatable или только для чтения (это зависит от возможности источника данных Open Database Connectivity (ODBC) и реализовали ли вы объемную строку. Чтобы обновить записи, которые могут `Open` быть изменены или `Requery` добавлены после вызова, позвоните функции члена объекта. Вызовите функцию `Close` члена объекта и уничтожьте объект, когда вы закончите с ним.

В производном `CRecordset` классе биржа полей записей (RFX) или объемная биржа полей записей (Bulk RFX) используется для поддержки чтения и обновления полей записи.

Для получения дополнительной информации о рекордных наборов и обмена [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)полями записей, [Recordset: Fetching Records in Bulk (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md) [см.](../../data/data-access-programming-mfc-atl.md) Для фокусировки на динасетах и снимках смотрите статьи [Dynaset](../../data/odbc/dynaset.md) и [Snapshot](../../data/odbc/snapshot.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CRecordset`

## <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

## <a name="crecordsetaddnew"></a><a name="addnew"></a>CRecordset::AddNew

Готовится к добавлению новой записи в таблицу.

```
virtual void AddNew();
```

### <a name="remarks"></a>Remarks

Необходимо позвонить в функцию участника [Requery,](#requery) чтобы увидеть недавно добавленную запись. Поля записи изначально являются null. (В терминологии базы данных Null означает «не имеющий ценности» и не является таким же, как NULL в СЗ.) Для завершения операции необходимо вызвать функцию участника [обновления.](#update) `Update`сохраняет изменения в источнике данных.

> [!NOTE]
> Если вы реализовали объем строки `AddNew`извлечения, вы не можете вызвать . Это приведет к неудавому утверждению. Хотя `CRecordset` класс не предоставляет механизм обновления объемных строк данных, вы можете написать свои `SQLSetPos`собственные функции с помощью функции ODBC API. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`AddNew`готовит новую пустую запись с использованием полевых данных записи. После вызова `AddNew`установите значения, которые вы хотите в данных полевых данных, в записи. (Для этой цели не нужно вызывать функцию члена `Edit` [Edit;](#edit) использовать только существующие записи.) При последующем `Update`вызове измененные значения в полях данных сохраняются на источнике данных.

> [!CAUTION]
> Если вы прокрутите новую запись перед вызовом, `Update`новая запись будет потеряна, и никаких предупреждений не дается.

Если источник данных поддерживает транзакции, можно сделать вызов `AddNew` частью транзакции. Для получения дополнительной информации [CDatabase](../../mfc/reference/cdatabase-class.md)о транзакциях см. Обратите внимание, что вы должны позвонить `AddNew` [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) перед вызовом .

> [!NOTE]
> Для dynasets, новые записи добавляются к рекорду, как последний рекорд. Добавленные записи не добавляются к снимкам; вы должны `Requery` позвонить, чтобы обновить рекорд.

Незаконно вызывать `AddNew` рекордсет, функция `Open` члена которого не была вызвана. A `CDBException` брошен, если `AddNew` вы призываете к набору записей, которые не могут быть придаты. Вы можете определить, является ли рекорд- updatable, позвонив [в CanAppend.](#canappend)

Для получения дополнительной информации, см. следующие статьи: [Запись: Как записи обновление записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [Запись: Добавление, обновление и удаляние записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), и [транзакции (ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Пример

Смотрите статью [Транзакция: Выполнение транзакции в наборе рекордов (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

## <a name="crecordsetcanappend"></a><a name="canappend"></a>CRecordset::CanAppend

Определяет, позволяет ли ранее открытый рекорд для добавления новых записей.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если рекорд позволяет добавлять новые записи; в противном случае 0. `CanAppend`вернется 0, если вы открыли рекорд, как только читать.

## <a name="crecordsetcanbookmark"></a><a name="canbookmark"></a>CRecordset::CanBookmark

Определяет, позволяет ли рекорддля пометить записи с помощью закладок.

```
BOOL CanBookmark() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если набор записей поддерживает закладки; в противном случае 0.

### <a name="remarks"></a>Remarks

Эта функция не `CRecordset::useBookmarks` зависит от опции в параметре *dwOptions* функции [Open](#open) member. `CanBookmark`указывает, является ли данный драйвер ODBC и закладки поддержки типа курсора. `CRecordset::useBookmarks`указывает, будут ли доступны закладки при условии их поддержки.

> [!NOTE]
> Закладки не поддерживаются на форвардных записях.

Для получения дополнительной информации о закладках и навигации, смотрите статьи [Recordset: Закладки и Абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [Рекордсет: Прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

## <a name="crecordsetcancel"></a><a name="cancel"></a>CRecordset::Отмена

Запросы на отмену источника данных либо асинхронной операции, или процесса из второго потока.

```
void Cancel();
```

### <a name="remarks"></a>Remarks

Обратите внимание, что классы MFC ODBC больше не используют асинхронную обработку; для выполнения асихронусной операции необходимо напрямую позвонить в функцию `SQLSetConnectOption`ODBC API. Для получения дополнительной информации, см. *ODBC SDK Programmer's Guide*

## <a name="crecordsetcancelupdate"></a><a name="cancelupdate"></a>CRecordset::CancelUpdate

Отменяет все ожидающие обновления, вызванные операцией [Edit](#edit) или [AddNew,](#addnew) до вызова [обновления.](#update)

```
void CancelUpdate();
```

### <a name="remarks"></a>Remarks

> [!NOTE]
> Эта функция участника не применима к рекордным наборам, использующим `Edit` `AddNew`объемные `Update`строки, так как такие записи не могут вызвать, или . Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Если включена автоматическая `CancelUpdate` проверка грязного поля, они восстановят `Edit` `AddNew` переменные участника к значениям, которые они имели до или были вызваны; в противном случае любые изменения стоимости останутся. По умолчанию автоматическая проверка поля включена при открытии набора записей. Чтобы отключить его, необходимо указать `CRecordset::noDirtyFieldCheck` параметр *dwOptions* функции [Open.](#open)

Для получения дополнительной информации об [Recordset: Adding, Updating, and Deleting Records (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)обновлении данных см.

## <a name="crecordsetcanrestart"></a><a name="canrestart"></a>CRecordset::CanRestart

Определяет, позволяет ли запись перезапустить свой запрос (обновить записи) по вызову функции `Requery` участника.

```
BOOL CanRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если повтор разрешен; в противном случае 0.

## <a name="crecordsetcanscroll"></a><a name="canscroll"></a>CRecordset::CanScroll

Определяет, позволяет ли запись прокрутки.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если рекордет позволяет прокрутки; в противном случае 0.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)прокрутке, см.

## <a name="crecordsetcantransact"></a><a name="cantransact"></a>CRecordset::CanTransact

Определяет, позволяет ли рекорд для транзакций.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если рекорд позволяет транзакции; в противном случае 0.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации, [см.](../../data/odbc/transaction-odbc.md)

## <a name="crecordsetcanupdate"></a><a name="canupdate"></a>CRecordset::CanUpdate

Определяет, можно ли обновить набор записей.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если рекорд может быть обновлен; в противном случае 0.

### <a name="remarks"></a>Remarks

Запись может быть прочитана только в том случае, если основной `CRecordset::readOnly` источник данных читается только или если вы указаны в параметре *dwOptions* при открытии набора записей.

## <a name="crecordsetcheckrowseterror"></a><a name="checkrowseterror"></a>CRecordset::CheckRowsetОшибка

Вызывается для обработки ошибок, генерируемых во время записи извлечения.

```
virtual void CheckRowsetError(RETCODE nRetCode);
```

### <a name="parameters"></a>Параметры

*nRetCode*<br/>
Код возврата функции ФУНКЦИи ODBC. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Remarks

Эта виртуальная функция члена обрабатывает ошибки, которые возникают при извлечении записей, и полезна во время извлечения строки. Вы можете рассмотреть `CheckRowsetError` возможность переопределения для реализации собственной обработки ошибок.

`CheckRowsetError`вызывается автоматически в операции навигации курсора, `Open`например, `Requery`или любой `Move` операции. Он передается возвратное значение функции `SQLExtendedFetch`ODBC API. В следующей таблице перечислены возможные значения параметра *nRetCode.*

|nRetCode|Описание|
|--------------|-----------------|
|SQL_SUCCESS|Функция выполнена успешно; дополнительная информация отсутствует.|
|SQL_SUCCESS_WITH_INFO|Функция завершена успешно, возможно, с несмертельной ошибкой. Дополнительную информацию можно `SQLError`получить, позвонив по телефону.|
|SQL_NO_DATA_FOUND|Все строки из набора результатов были извлечены.|
|SQL_ERROR|Функция не сработала. Дополнительную информацию можно `SQLError`получить, позвонив по телефону.|
|SQL_INVALID_HANDLE|Функция не сработала из-за недействительной ручки среды, ручки соединения или ручки оператора. Это указывает на ошибку программирования. Дополнительная информация `SQLError`от .|
|SQL_STILL_EXECUTING|Функция, которая была начата асинхронно, все еще исполняется. Обратите внимание, что по умолчанию MFC никогда не передаст это `CheckRowsetError`значение; МФЦ будет `SQLExtendedFetch` звонить до тех пор, пока не вернется SQL_STILL_EXECUTING.|

Для получения `SQLError`дополнительной информации о , см. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetclose"></a><a name="close"></a>CRecordset::Закрыть

Закрывает рекорд.

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

ODBC HSTMT и вся память рамки, выделенные для рекорда расположены. Обычно после `Close`вызова вы удаляете объект регистрации C', если он был выделен с **новым**.

Вы можете `Open` позвонить `Close`еще раз после вызова . Это позволяет повторно использовать объект записи. Альтернативой является `Requery`вызов .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]

## <a name="crecordsetcrecordset"></a><a name="crecordset"></a>CRecordset::CRecordset

Формирует объект `CRecordset`.

```
CRecordset(CDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Параметры

*pDatabase*<br/>
Содержит указатель `CDatabase` на объект или значение NULL. Если не NULL `CDatabase` и `Open` функция члена объекта не была вызвана для подключения его к источнику данных, `Open` запись пытается открыть его для вас во время его собственного звонка. Если вы передаете `CDatabase` NULL, объект строится и подключается для вас, используя информацию об источнике данных, указанную при создании класса recordset с ClassWizard.

### <a name="remarks"></a>Remarks

Вы можете `CRecordset` использовать непосредственно или получить тип `CRecordset`для конкретного приложения из . Вы можете использовать ClassWizard для получения классов записей.

> [!NOTE]
> Полученный класс *должен* поставлять свой собственный конструктор. В конструкторе вашего производного `CRecordset::CRecordset`класса позвоните в конструктор, передав ему соответствующие параметры.

Передайте NULL своему конструктору `CDatabase` записей, чтобы объект был построен и подключен для вас автоматически. Это полезное сокращение, которое не требует от `CDatabase` вас, чтобы построить и подключить объект до построения вашего рекорда.

### <a name="example"></a>Пример

Для получения дополнительной информации см. [Recordset: Declaring a Class for a Table (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)

## <a name="crecordsetdelete"></a><a name="delete"></a>CRecordset::Delete

Удаляет текущую запись.

```
virtual void Delete();
```

### <a name="remarks"></a>Remarks

После успешного удаления члены полевых данных записи устанавливаются на значение Null, и `Move` необходимо явно вызвать одну из функций, чтобы отойти от удаленной записи. После того, как вы отойдите от удаленной записи, вернуться к ней невозможно. Если источник данных поддерживает транзакции, можно сделать `Delete` вызов частью транзакции. Для получения дополнительной информации, [см.](../../data/odbc/transaction-odbc.md)

> [!NOTE]
> Если вы реализовали объем строки `Delete`извлечения, вы не можете вызвать . Это приведет к неудавому утверждению. Хотя `CRecordset` класс не предоставляет механизм обновления объемных строк данных, вы можете написать свои `SQLSetPos`собственные функции с помощью функции ODBC API. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!CAUTION]
> Запись должна быть updatable и не должно быть действительным током `Delete`записи в recordset, когда вы звоните; в противном случае возникает ошибка. Например, если вы удалите запись, но не `Delete` прокрутите новую запись перед вызовом снова, `Delete` бросает [CDBException](../../mfc/reference/cdbexception-class.md).

В отличие от [AddNew](#addnew) и `Delete` [Edit,](#edit)вызов не сопровождается призывом к [обновлению](#update). При `Delete` сбывом вызове члены данных полевого поля остаются неизменными.

### <a name="example"></a>Пример

В этом примере отображается набор записей, созданный на кадре функции. Пример предполагает существование `m_dbCust`переменной члена типа, `CDatabase` уже подключенной к источнику данных.

[!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]

## <a name="crecordsetdobulkfieldexchange"></a><a name="dobulkfieldexchange"></a>CRecordset::DoBulkFieldExchange

Вызывается для обмена объемными строками данных от источника данных до уровня записи. Реализует объемную биржу месторождений (Bulk RFX).

```
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект [CFieldExchange.](../../mfc/reference/cfieldexchange-class.md) В рамках уже будет создан этот объект для определения контекста для операции по обмену полями.

### <a name="remarks"></a>Remarks

При реализации навалочных строк, фреймворк вызывает эту функцию участника для автоматической передачи данных из источника данных на объект записи. `DoBulkFieldExchange`также связывает членов параметра данных, если таковые имеются, с заполнителями параметров в строке оператора S'L для выбора набора записей.

Если навалочный ряд извлечения не реализован, фреймворк вызывает [DoFieldExchange.](#dofieldexchange) Для реализации навалочных строк `CRecordset::useMultiRowFetch` извлечения необходимо указать опцию параметра *dwOptions* в функции [open](#open) member.

> [!NOTE]
> `DoBulkFieldExchange`доступен только в том случае, `CRecordset`если вы используете класс, полученный из. Если вы создали объект записи `CRecordset`непосредственно из, вы должны вызвать функцию участника [GetFieldValue](#getfieldvalue) для получения данных.

Массовая биржа месторождений (Bulk RFX) похожа на биржу рекордных полей (RFX). Данные автоматически передаются из источника данных на объект регистрации. Тем не менее, `Delete`вы `Update` не можете вызвать, `AddNew` `Edit`, или перенести изменения обратно в источник данных. Класс `CRecordset` в настоящее время не обеспечивает механизм обновления объемных строк данных; однако, вы можете написать свои собственные функции с помощью функции `SQLSetPos`ODBC API.

Обратите внимание, что ClassWizard не поддерживает оптовый обмен полями записей; поэтому необходимо переопределить `DoBulkFieldExchange` вручную, написав вызовы на функции Bulk RFX. Для получения дополнительной информации об [Record Field Exchange Functions](../../mfc/reference/record-field-exchange-functions.md)этих функциях, см.

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Для получения соответствующей [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md)информации см.

## <a name="crecordsetdofieldexchange"></a><a name="dofieldexchange"></a>CRecordset::DoFieldExchange

Вызывается для обмена данными (в обоих направлениях) между полевыми данными членов регистрации и соответствующей записью об источнике данных. Реализует обмен рекордными полями (RFX).

```
virtual void DoFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Параметры

*Pfx*<br/>
Указатель на объект [CFieldExchange.](../../mfc/reference/cfieldexchange-class.md) В рамках уже будет создан этот объект для определения контекста для операции по обмену полями.

### <a name="remarks"></a>Remarks

Когда объемная строка извлечения не реализована, фреймворк вызывает эту функцию участника для автоматического обмена данными между членами данных поля объекта записи и соответствующими столбцов текущей записи на источнике данных. `DoFieldExchange`также связывает членов параметра данных, если таковые имеются, с заполнителями параметров в строке оператора S'L для выбора набора записей.

Если объемная строка извлечения реализована, фреймворк вызывает [DoBulkFieldExchange](#dobulkfieldexchange). Для реализации навалочных строк `CRecordset::useMultiRowFetch` извлечения необходимо указать опцию параметра *dwOptions* в функции [open](#open) member.

> [!NOTE]
> `DoFieldExchange`доступен только в том случае, `CRecordset`если вы используете класс, полученный из. Если вы создали объект записи `CRecordset`непосредственно из, вы должны вызвать функцию участника [GetFieldValue](#getfieldvalue) для получения данных.

Обмен полевыми данными, называемый обменом данными (RFX), работает в обоих направлениях: от полевых данных объекта записи до полей записи на источнике данных и от записи об источнике данных до объекта записи.

Единственное действие, необходимое обычно `DoFieldExchange` для реализации для вашего производного класса записей, это создание класса с ClassWizard и указание имен и типов данных членов полевых данных. Вы также можете добавить код к тому, что пишет ClassWizard, чтобы указать членов параметров или иметь дело с любыми столбцов, которые вы связываете динамически. Для получения дополнительной информации см. [Recordset: Dynamically Binding Data Columns (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md)

Когда вы объявляете свой класс производных записей с `DoFieldExchange` ClassWizard, мастер записывает переопределение для вас, который напоминает следующий пример:

[!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]

Для получения дополнительной информации о функциях RFX, см. [Record Field Exchange Functions](../../mfc/reference/record-field-exchange-functions.md)

Для получения более дополнительных примеров и подробностей о `DoFieldExchange`, см. [Record Field Exchange: How RFX Works](../../data/odbc/record-field-exchange-how-rfx-works.md) Для получения общей информации о [Record Field Exchange](../../data/odbc/record-field-exchange-rfx.md)RFX, см.

## <a name="crecordsetedit"></a><a name="edit"></a>CRecordset::Edit

Позволяет изменять текущую запись.

```
virtual void Edit();
```

### <a name="remarks"></a>Remarks

После вызова `Edit`можно изменить составиных данных поля, непосредственно сбросив их значения. Операция завершается, когда вы впоследствии вызываете функцию участника [обновления,](#update) чтобы сохранить изменения в источнике данных.

> [!NOTE]
> Если вы реализовали объем строки `Edit`извлечения, вы не можете вызвать . Это приведет к неудавому утверждению. Хотя `CRecordset` класс не предоставляет механизм обновления объемных строк данных, вы можете написать свои `SQLSetPos`собственные функции с помощью функции ODBC API. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`Edit`сохраняет значения членов данных записей. Если вы `Edit`звоните, вносят изменения, а затем звоните `Edit` снова, значения `Edit` записи восстанавливаются до того, что они были до первого звонка.

В некоторых случаях можно обновить столбец, сделав его недействительным (не содержащим данных). Для этого позвоните [в SetFieldNull](#setfieldnull) с параметром TRUE, чтобы отметить поле Null; это также приводит к обновлению столбца. Если вы хотите, чтобы поле было записано в источник данных, даже если его значение не изменилось, позвоните [в SetFieldDirty](#setfielddirty) с параметром TRUE. Это работает, даже если поле имело значение Null.

Если источник данных поддерживает транзакции, можно сделать `Edit` вызов частью транзакции. Обратите внимание, что вы должны позвонить `Edit` [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) до вызова и после открытия набора записей. Также обратите внимание, что вызов [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) не является заменой для вызова `Update` для завершения `Edit` операции. Для получения дополнительной информации [CDatabase](../../mfc/reference/cdatabase-class.md)о транзакциях см.

В зависимости от текущего режима блокировки, обновляемая запись может быть заблокирована `Edit` до тех пор, пока вы не позвоните `Update` или не прокрутите другую запись, или она может быть заблокирована только во время `Edit` вызова. Вы можете изменить режим [блокировки с setLockingMode](#setlockingmode).

Предыдущее значение текущей записи восстанавливается, если вы `Update`прокрутите новую запись перед вызовом. A `CDBException` брошен, если `Edit` вы призываете к записи, которая не может быть обновлена или если нет текущей записи.

Для получения дополнительной информации смотрите статьи [Транзакция (ODBC)](../../data/odbc/transaction-odbc.md) и [запись: Блокировка записей (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]

## <a name="crecordsetflushresultset"></a><a name="flushresultset"></a>CRecordset::FlushResultSet

Извлекает следующий набор результатов предопределенного запроса (процедура хранения), если есть несколько наборов результатов.

```
BOOL FlushResultSet();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если есть больше наборов результатов, которые будут извлечены; в противном случае 0.

### <a name="remarks"></a>Remarks

Вы должны `FlushResultSet` звонить только тогда, когда вы полностью закончили с курсором на текущий набор результатов. Обратите внимание, что при получении `FlushResultSet`следующего результата, установленного вызывая, курсор не действителен в этом наборе результатов; вы должны вызвать функцию `FlushResultSet`участника [MoveNext](#movenext) после вызова.

Если в предопределенном запросе используется параметр вывода или параметры `FlushResultSet` ввода/вывода, необходимо вызвать вызов до тех пор, пока он не вернется `FALSE` (значение 0), чтобы получить эти значения параметров.

`FlushResultSet`вызывает функцию `SQLMoreResults`API ODBC. Если `SQLMoreResults` возвращается SQL_ERROR `FlushResultSet` или SQL_INVALID_HANDLE, то будет бросать исключение. Для получения `SQLMoreResults`дополнительной информации о , см.

Ваша сохраненная процедура должна иметь связанные `FlushResultSet`поля, если вы хотите позвонить.

### <a name="example"></a>Пример

Следующий код предполагает, `COutParamRecordset` `CRecordset`что это объект, полученный на основе заданного запроса с параметром ввода и параметром вывода, и имеющий несколько наборов результатов. Обратите внимание на структуру переопределения [DoFieldExchange.](#dofieldexchange)

[!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]

[!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]

## <a name="crecordsetgetbookmark"></a><a name="getbookmark"></a>CRecordset::GetBookmark

Получает значение закладки для текущей записи.

```
void GetBookmark(CDBVariant& varBookmark);
```

### <a name="parameters"></a>Параметры

*varBookmark*<br/>
Ссылка на объект [CDBVariant,](../../mfc/reference/cdbvariant-class.md) представляющий закладку на текущей записи.

### <a name="remarks"></a>Remarks

Чтобы определить, поддерживаются ли закладки на рекорде, позвоните [в CanBookmark](#canbookmark). Чтобы сделать закладки доступными, `CRecordset::useBookmarks` если они поддерживаются, необходимо установить опцию в параметре *dwOptions* функции [Open](#open) member.

> [!NOTE]
> Если закладки не поддерживаются `GetBookmark` или недоступны, вызов приведет к тому, что исключение будет брошено. Закладки не поддерживаются на форвардных записях.

`GetBookmark`присваивает `CDBVariant` объекту значение закладки для текущей записи. Чтобы вернуться к этой записи в любое время после перехода `CDBVariant` к другой записи, позвоните [SetBookmark](#setbookmark) с соответствующим объектом.

> [!NOTE]
> После определенных операций рекорда закладки могут быть недействительными. Например, если `GetBookmark` вы `Requery`звоните с последующим, вы не `SetBookmark`сможете вернуться к записи с . Позвоните [CDatabase::GetBookmarkPersistenceenceenceenceenceence,](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) чтобы проверить, можете ли вы безопасно позвонить `SetBookmark`.

Для получения дополнительной информации о закладках и навигации, смотрите статьи [Recordset: Закладки и Абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [Рекордсет: Прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

## <a name="crecordsetgetdefaultconnect"></a><a name="getdefaultconnect"></a>CRecordset::GetDefaultConnect

Вызывается, чтобы получить строку соединения по умолчанию.

```
virtual CString GetDefaultConnect();
```

### <a name="return-value"></a>Возвращаемое значение

A, `CString` содержащий строку соединения по умолчанию.

### <a name="remarks"></a>Remarks

Платформа вызывает эту функцию участника, чтобы получить строку соединения по умолчанию для источника данных, на котором основан рекорд. ClassWizard реализует эту функцию для вас, идентифицируя тот же источник данных, который вы используете в ClassWizard для получения информации о таблицах и столбцах. Вероятно, вам будет удобно полагаться на это соединение по умолчанию при разработке приложения. Но подключение по умолчанию может быть неподходящим для пользователей приложения. Если это так, вы должны повторно реализовать эту функцию, отбрасывая версию ClassWizard. Для получения дополнительной информации о [Data Source (ODBC)](../../data/odbc/data-source-odbc.md)строках соединения см.

## <a name="crecordsetgetdefaultsql"></a><a name="getdefaultsql"></a>CRecordset::GetDefaultS'L

Вызывается, чтобы получить строку по умолчанию S'L для выполнения.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Возвращаемое значение

A, `CString` содержащий выписку по умолчанию.

### <a name="remarks"></a>Remarks

Платформа вызывает эту функцию участника, чтобы получить заявление по умолчанию, на котором основан освоен рекорд. Это может быть имя таблицы или выписка s'L **SELECT.**

Вы косвенно определяете заявление по умолчанию, объявляя класс записей с ClassWizard, и ClassWizard выполняет эту задачу за вас.

Если вам нужна строка выписки s-L для собственного использования, позвоните по вызову, `GetSQL`который возвращает выписку, используемую для выбора записей, используемых при его открытии. Можно отсеять строку по умолчанию s'L в переопределение вашего `GetDefaultSQL`класса. Например, можно указать вызов к заданного запросу с помощью оператора **CALL.** (Обратите внимание, однако, `GetDefaultSQL`что при изменении, вам также необходимо изменить, `m_nFields` чтобы соответствовать числу столбцов в источнике данных.)

Для получения дополнительной информации см. [Recordset: Declaring a Class for a Table (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md)

> [!CAUTION]
> Имя таблицы будет пустым, если фреймворк не может определить имя таблицы, если было предоставлено несколько названий таблицы, или если заявление **CALL** не может быть интерпретировано. Обратите внимание, что при использовании оператора **CALL** не следует вставлять пробел между фигурной скобкой и ключевым словом **CALL,** а также не следует вставлять белое пространство до фигурной скобки или перед ключевым словом **SELECT** в заявлении **SELECT.**

## <a name="crecordsetgetfieldvalue"></a><a name="getfieldvalue"></a>CRecordset::GetFieldValue

Извлекает полевые данные в текущей записи.

```
void GetFieldValue(
    LPCTSTR lpszName,
    CDBVariant& varValue,
    short nFieldType = DEFAULT_FIELD_TYPE);

void GetFieldValue(
    short nIndex,
    CDBVariant& varValue,
    short nFieldType = DEFAULT_FIELD_TYPE);

void GetFieldValue(
    short nIndex,
    CStringA& strValue);

void GetFieldValue(
    short nIndex,
    CStringW& strValue);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Название поля.

*varValu*e Ссылка на объект [CDBVariant,](../../mfc/reference/cdbvariant-class.md) который будет хранить значение поля.

*nFieldType*<br/>
Тип данных ODBC C поля. Использование значения по умолчанию, DEFAULT_FIELD_TYPE, заставляет `GetFieldValue` определить тип данных C из типа данных S'L, на основе следующей таблицы. В противном случае можно указать тип данных напрямую или выбрать совместимый тип данных; например, можно хранить любой тип данных в SQL_C_CHAR.

|Тип данных C|Тип данных SQL|
|-----------------|-------------------|
|SQL_C_BIT|SQL_BIT|
|SQL_C_UTINYINT|SQL_TINYINT|
|SQL_C_SSHORT|SQL_SMALLINT|
|SQL_C_SLONG|SQL_INTEGER|
|SQL_C_FLOAT|SQL_REAL|
|SQL_C_DOUBLE|SQL_FLOATSQL_DOUBLE|
|SQL_C_TIMESTAMP|SQL_DATESQL_TIMESQL_TIMESTAMP|
|SQL_C_CHAR|SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR|
|SQL_C_BINARY|SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY|

Более подробную информацию о типах данных ODBC можно узнать в приложении D От Windows SDK по темам «Типы данных» и «Типы C данных».

*Nindex*<br/>
Индекс поля с нулевым уровнем.

*strValue*<br/>
Ссылка на объект [CString,](../../atl-mfc-shared/reference/cstringt-class.md) который будет хранить значение поля, преобразованное в текст, независимо от типа данных поля.

### <a name="remarks"></a>Remarks

Вы можете посмотреть поле по имени или по индексу. Значение поля можно хранить либо `CDBVariant` в `CString` объекте, либо в объекте.

Если вы реализовали объемный ряд извлечения, текущая запись всегда позиционируется на первой записи в строке. Чтобы `GetFieldValue` использовать запись в заданном наборе строк, необходимо сначала вызвать функцию члена [SetRowsetCursorPosition,](#setrowsetcursorposition) чтобы переместить курсор в нужную строку в пределах этого строки. Тогда `GetFieldValue` позвони в этот ряд. Для реализации навалочных строк `CRecordset::useMultiRowFetch` извлечения необходимо указать опцию параметра *dwOptions* в функции [open](#open) member.

Можно использовать `GetFieldValue` для динамического получения полей во время выполнения, а не статически связывая их во время проектирования. Например, если вы объявили объект `CRecordset`записи непосредственно `GetFieldValue` из, вы должны использовать для извлечения данных поля; обмен поля записи (RFX), или объемная биржа поля записи (Bulk RFX), не реализуется.

> [!NOTE]
> Если вы объявляете объект регистрации, `CRecordset`не вытекая из, не загружайте библиотеку ODBC Cursor. Библиотека курсора требует, чтобы запись была иметь по крайней мере одну связанную колонку; однако при `CRecordset` непосредственном использовании ни одна из столбцов не связана. Участник [функции CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) и [CDatabase:: Открытый](../../mfc/reference/cdatabase-class.md#open) контроль ли библиотека курсора будет загружена.

`GetFieldValue`вызывает функцию `SQLGetData`API ODBC. Если драйвер выводит значение SQL_NO_TOTAL для фактической длины значения поля, `GetFieldValue` выбрасывает исключение. Для получения `SQLGetData`дополнительной информации о , см.

### <a name="example"></a>Пример

Следующий пример кода иллюстрирует `GetFieldValue` вызовы для объекта, `CRecordset`объявленного непосредственно из .

[!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]

> [!NOTE]
> В отличие от `CDaoRecordset`класса `CRecordset` DAO, не имеет функции `SetFieldValue` участника. Если вы создаете `CRecordset`объект непосредственно из, он эффективно читать только.

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetgetodbcfieldcount"></a><a name="getodbcfieldcount"></a>CRecordset::GetODBCFieldCount

Извлекает общее количество полей в объекте записи.

```
short GetODBCFieldCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество полей в рекорде.

### <a name="remarks"></a>Remarks

Для получения дополнительной информации о [Recordset: Creating and Closing Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)создании рекордов, см.

## <a name="crecordsetgetodbcfieldinfo"></a><a name="getodbcfieldinfo"></a>CRecordset::GetODBCFieldInfo

Получает информацию о полях в рекордном наборе.

```
void GetODBCFieldInfo(
    LPCTSTR lpszName,
    CODBCFieldInfo& fieldinfo);

void GetODBCFieldInfo(
    short nIndex,
    CODBCFieldInfo& fieldinfo);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Название поля.

*Fieldinfo*<br/>
Ссылка на `CODBCFieldInfo` структуру.

*Nindex*<br/>
Индекс поля с нулевым уровнем.

### <a name="remarks"></a>Remarks

Одна из версий функции позволяет искать поле по имени. Другая версия позволяет искать поле по индексу.

Для описания возвращенной информации [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md) см.

Для получения дополнительной информации о [Recordset: Creating and Closing Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md)создании рекордов, см.

## <a name="crecordsetgetrecordcount"></a><a name="getrecordcount"></a>CRecordset::GetRecordCount

Определяет размер рекорда.

```
long GetRecordCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество записей в рекорде; 0, если рекорд не содержит записей; или -1, если количество записей не может быть определено.

### <a name="remarks"></a>Remarks

> [!CAUTION]
> Количество записей поддерживается как "высокая отметка воды", самый высокий номер записи еще видели, как пользователь движется через записи. Общее количество записей известно только после того, как пользователь вышел за пределы последней записи. По причинам производительности подсчет не обновляется при вызове. `MoveLast` Чтобы считать записи `MoveNext` самостоятельно, `IsEOF` позвоните неоднократно, пока не вернется ненулевой. Добавление записи `CRecordset:AddNew` `Update` через и увеличивает количество; удаляя запись `CRecordset::Delete` с помощью уменьшения количества.

## <a name="crecordsetgetrowsetsize"></a><a name="getrowsetsize"></a>CRecordset::GetRowsetSize

Получает текущую настройку для количества строк, которые вы хотите получить во время данного получения.

```
DWORD GetRowsetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество строк для получения во время данного получения.

### <a name="remarks"></a>Remarks

Если вы используете объемстроки извлечения, размер строки по умолчанию при открытии рекорда составляет 25; в противном случае, это 1.

Для реализации навалочных строк `CRecordset::useMultiRowFetch` извлечения необходимо указать опцию в параметре *dwOptions* функции [open](#open) member. Чтобы изменить настройку для размера рядового набора, позвоните [SetRowsetSize.](#setrowsetsize)

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetgetrowsfetched"></a><a name="getrowsfetched"></a>CRecordset::GetRowsFetched

Определяет, сколько записей было получено после получения.

```
DWORD GetRowsFetched() const;
```

### <a name="return-value"></a>Возвращаемое значение

Количество строк, извлеченных из источника данных после данного получения.

### <a name="remarks"></a>Remarks

Это полезно, когда вы реализовали объем строки извлечения. Размер строки обычно указывает, сколько строк будет извлечено из привитого; однако общее количество строк в наборе записей также влияет на количество строк, которые будут получены в строке. Например, если в записи установлено 10 записей с параметром размера строки `MoveNext` 4, то циклирование через запись путем вызова приведет к тому, что в финальном ряде будет всего 2 записи.

Для реализации навалочных строк `CRecordset::useMultiRowFetch` извлечения необходимо указать опцию в параметре *dwOptions* функции [open](#open) member. Чтобы указать размер строки, позвоните [SetRowsetSize.](#setrowsetsize)

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]

## <a name="crecordsetgetrowstatus"></a><a name="getrowstatus"></a>CRecordset::GetRowStatus

Получает статус строки в текущем наборе строк.

```
WORD GetRowStatus(WORD wRow) const;
```

### <a name="parameters"></a>Параметры

*wRow*<br/>
Одноразовая позиция строки в текущем ряде. Это значение может варьироваться от 1 до размера строки.

### <a name="return-value"></a>Возвращаемое значение

Значение состояния для строки. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Remarks

`GetRowStatus`возвращает значение, указывавое либо изменение состояния в строку, так как оно в последний раз было извлечено из источника данных, или что не было получено строки, соответствующей *wRow.* В следующей таблице перечислены возможные возвращаемые значения.

|Значение состояния|Описание|
|------------------|-----------------|
|SQL_ROW_SUCCESS|Строка не изменилась.|
|SQL_ROW_UPDATED|Строка была обновлена.|
|SQL_ROW_DELETED|Строка была удалена.|
|SQL_ROW_ADDED|Строка добавлена.|
|SQL_ROW_ERROR|Строка невозвратна из-за ошибки.|
|SQL_ROW_NOROW|Существует не строка, которая соответствует *wRow*.|

Для получения дополнительной информации см. `SQLExtendedFetch`

## <a name="crecordsetgetstatus"></a><a name="getstatus"></a>CRecordset::GetStatus

Определяет индекс текущего рекорда в рекорде и был ли замечен последний рекорд.

```
void GetStatus(CRecordsetStatus& rStatus) const;
```

### <a name="parameters"></a>Параметры

*rStatus*<br/>
Ссылка на объект `CRecordsetStatus`. Дополнительные сведения см. в разделе «Примечания».

### <a name="remarks"></a>Remarks

`CRecordset`попытки отследить индекс, но при некоторых обстоятельствах это может оказаться невозможным. Смотрите [GetRecordCount](#getrecordcount) для объяснения.

Структура `CRecordsetStatus` имеет следующую форму:

```cpp
struct CRecordsetStatus
{
    long m_lCurrentRecord;
    BOOL m_bRecordCountFinal;
};
```

Два члена `CRecordsetStatus` имеют следующие значения:

- `m_lCurrentRecord`Содержит нулевой индекс текущего рекорда в рекордном, если известно. Если индекс не может быть определен, этот участник содержит AFX_CURRENT_RECORD_UNDEFINED (-2). Если `IsBOF` это правда (пустой рекордили или попытка `m_lCurrentRecord` прокрутки до первого записи), то устанавливается AFX_CURRENT_RECORD_BOF (-1). Если на первом рекорде, то он установлен на 0, второй рекорд 1, и так далее.

- `m_bRecordCountFinal`Nonzero, если общее количество записей в рекорде было определено. Как правило, это должно быть достигнуто, начиная с `MoveNext` `IsEOF` начала набора записей и призывая до тех пор, пока возвращается ненулевой. Если этот участник равен нулю, `GetRecordCount`то количество записей, возвращенное, если не -1, является лишь «высокой отметкой воды» в записях.

## <a name="crecordsetgetsql"></a><a name="getsql"></a>CRecordset::GetS'L

Вызовите эту функцию участника, чтобы получить выписку по S'L, которая использовалась для выбора записей записей, когда он был открыт.

```
const CString& GetSQL() const;
```

### <a name="return-value"></a>Возвращаемое значение

**Конст** ссылка `CString` на, который содержит заявление S'L.

### <a name="remarks"></a>Remarks

Как правило, это будет заявление S'L **SELECT.** Строка, `GetSQL` возвращенная только прочитанной.

Строка, `GetSQL` которую возвращается, обычно отличается от любой строки, которую `Open` вы, возможно, перешли к набору записей в параметре *lpszS'L* функции участника. Это происходит потому, что в наборе записей построена полная выписка по S'L, основанная на `Open`том, что вы передали, что вы указали в ClassWizard, что вы, возможно, указали в `m_strFilter` и членов `m_strSort` данных, и любых параметрах, которые вы могли бы указать. Подробнее о том, как запись строит это заявление, [Recordset: How Recordsets Select Records (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)см.

> [!NOTE]
> Вызов эту функцию участника только после вызова [Open](#open).

## <a name="crecordsetgettablename"></a><a name="gettablename"></a>CRecordset::GetTableName

Получает название таблицы S'L, на которой основан запрос записи.

```
const CString& GetTableName() const;
```

### <a name="return-value"></a>Возвращаемое значение

**Ссылка** на `CString` имя таблицы, если запись основана на таблице; в противном случае, пустая строка.

### <a name="remarks"></a>Remarks

`GetTableName`действителен только в том случае, если запись основана на таблице, а не на соединении нескольких таблиц или предопределенном запросе (процедура хранения). Имя читается только для чтения.

> [!NOTE]
> Вызов эту функцию участника только после вызова [Open](#open).

## <a name="crecordsetisbof"></a><a name="isbof"></a>CRecordset::IsBOF

Возвращает ненулевой, если рекорд был расположен до первой записи. Отсутствует текущая запись.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если запись не содержит записей или если вы прокрутили назад до первой записи; в противном случае 0.

### <a name="remarks"></a>Remarks

Позвоните в эту функцию участника, прежде чем прокрутите от записи к записи, чтобы узнать, прошли ли вы до первой записи рекорда. Вы также `IsBOF` можете `IsEOF` использовать вместе с определить, содержит ли рекорды какие-либо записи или пусто. Сразу после `Open`вызова, если запись не `IsBOF` содержит записей, возвращается ненулевой. Когда вы открываете рекорд, который имеет по крайней мере `IsBOF` одну запись, первая запись — это текущая запись и возвращает 0.

Если первая запись текущей записи, и вы звоните, `MovePrev` `IsBOF` будет впоследствии вернуться ненулевой. Если `IsBOF` возвращается ненулевой и вы звоните, `MovePrev`ошибка происходит. Если `IsBOF` возврат ненулевой, текущая запись не определена, и любое действие, требующее текущей записи, приведет к ошибке.

### <a name="example"></a>Пример

Этот пример `IsBOF` `IsEOF` использует и для обнаружения пределов записи, как код прокручивает запись в обоих направлениях.

[!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]

## <a name="crecordsetisdeleted"></a><a name="isdeleted"></a>CRecordset::Isdeleted

Определяет, была ли удалена текущая запись.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если запись расположена на удаленной записи; в противном случае 0.

### <a name="remarks"></a>Remarks

Если вы прокрутите запись и `IsDeleted` возвращаете TRUE (nonzero), то вы должны прокрутить другую запись, прежде чем вы сможете выполнить любые другие операции записи.

Результат `IsDeleted` зависит от многих факторов, таких как тип записи, является ли ваш рекорд, updatable, указываете ли вы `CRecordset::skipDeletedRecords` вариант, когда вы открыли запись, является ли ваш драйвер пакеты удаленных записей, и есть ли несколько пользователей.

Для получения `CRecordset::skipDeletedRecords` дополнительной информации о [Open](#open) упаковке драйверов см.

> [!NOTE]
> Если вы реализовали объем строки извлечения, вы не должны звонить `IsDeleted`. Вместо этого позвоните в функцию участника [GetRowStatus.](#getrowstatus) Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetiseof"></a><a name="iseof"></a>CRecordset::IsEOF

Возвращает ненулевой, если рекорд был расположен после последней записи. Отсутствует текущая запись.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если запись не содержит записей или если вы прокрутили за пределами последней записи; в противном случае 0.

### <a name="remarks"></a>Remarks

Позвоните в эту функцию участника при прокрутке от записи к записи, чтобы узнать, вышли ли вы за рамки последней записи рекорда. Можно также `IsEOF` использовать для определения того, содержит ли запись какие-либо записи или он пуст. Сразу после `Open`вызова, если запись не `IsEOF` содержит записей, возвращается ненулевой. Когда вы открываете рекорд, который имеет по крайней мере `IsEOF` одну запись, первая запись — это текущая запись и возвращает 0.

Если последняя запись — это текущая `IsEOF` запись при вызове, `MoveNext`то она впоследствии вернется ненулевой. Если `IsEOF` возвращается ненулевой и вы звоните, `MoveNext`ошибка происходит. Если `IsEOF` возврат ненулевой, текущая запись не определена, и любое действие, требующее текущей записи, приведет к ошибке.

### <a name="example"></a>Пример

Смотрите пример [IsBOF](#isbof).

## <a name="crecordsetisfielddirty"></a><a name="isfielddirty"></a>CRecordset::IsfieldDirty

Определяет, был ли изменен указанный член данных поля с момента [вызова Edit](#edit) или [AddNew.](#addnew)

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
Указатель на участника данных поля, состояние которого вы хотите проверить, или NULL, чтобы определить, является ли какое-либо из полей грязным.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если указанный член данных поля изменился после вызова `AddNew` или `Edit`; в противном случае 0.

### <a name="remarks"></a>Remarks

Данные во всех грязных полевых данных будут переданы в запись источника данных, когда `CRecordset` текущая запись `Edit` обновляется вызовом к функции участника `AddNew` [обновления](#update) (после вызова или).

> [!NOTE]
> Эта функция члена не применима к рекордным наборам, использующим извлечения объемных строк. Если вы реализовали объем строки извлечения, то `IsFieldDirty` всегда будет возвращать FALSE и приведет к неудалось утверждение. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Вызов `IsFieldDirty` сбросить эффекты предыдущих вызовов [в SetFieldDirty,](#setfielddirty) так как грязный статус поля переоценен. В `AddNew` случае, если текущее значение поля отличается от псевдонультного значения, статус поля устанавливается грязным. В `Edit` этом случае, если значение поля отличается от кэшированного значения, то статус поля устанавливается грязным.

`IsFieldDirty`реализуется через [DoFieldExchange](#dofieldexchange).

Для получения дополнительной информации о [Recordset: How Recordsets Select Records (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)грязном флаге, см.

## <a name="crecordsetisfieldnull"></a><a name="isfieldnull"></a>CRecordset::IsFieldNull

Возвращает ненулевой, если указанное поле в текущей записи Null (не имеет значения).

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
Указатель на участника данных поля, состояние которого вы хотите проверить, или NULL, чтобы определить, является ли какое-либо из полей null.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если указанный член данных поля помечен как Null; в противном случае 0.

### <a name="remarks"></a>Remarks

Вызовите эту функцию участника, чтобы определить, был ли указанный полевой член данных набора записей помечен как Null. (В терминологии базы данных Null означает «не имеющий ценности» и не является таким же, как NULL в СЗ.) Если участник полевых данных помечен как Null, он интерпретируется как столбец текущей записи, для которого нет значения.

> [!NOTE]
> Эта функция члена не применима к рекордным наборам, использующим извлечения объемных строк. Если вы реализовали объем строки извлечения, то `IsFieldNull` всегда будет возвращать FALSE и приведет к неудалось утверждение. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`IsFieldNull`реализуется через [DoFieldExchange](#dofieldexchange).

## <a name="crecordsetisfieldnullable"></a><a name="isfieldnullable"></a>CRecordset::IsfieldNullable

Возвращает ненулевой, если указанное поле в текущем отчете может быть установлено на Null (не имеюще значения).

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
Указатель на участника данных поля, состояние которого вы хотите проверить, или NULL, чтобы определить, может ли какое-либо из полей быть установлено на значение Null.

### <a name="remarks"></a>Remarks

Вызовите эту функцию участника, чтобы определить, является ли указанный участник данных поля «недействительным» (может быть установлен на значение Null; СЗ НУЛЛ не то же самое, что Null, что, в терминологии базы данных, означает "не имеет значения").

> [!NOTE]
> Если вы реализовали объем строки `IsFieldNullable`извлечения, вы не можете вызвать . Вместо этого позвоните в функцию участника [GetODBCFieldInfo,](#getodbcfieldinfo) чтобы определить, может ли поле быть установлено на значение Null. Обратите внимание, что `GetODBCFieldInfo`вы всегда можете вызвать, независимо от того, были ли вы реализованы объем строки извлечения. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Поле, которое не может быть null, должно иметь значение. Если вы попытаетесь установить такое поле для Null при добавлении или обновлении записи, источник данных отклоняет добавление или обновление, и [обновление](#update) будет бросать исключение. Исключение происходит при `Update`вызове, а не при вызове [SetFieldNull.](#setfieldnull)

Использование NULL для первого аргумента функции `outputColumn` будет применять `param` функцию только к полям, а не полям. Например, вызов

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

установит только `outputColumn` поля NULL; `param` поля не будут затронуты.

Для работы на `param` полях необходимо предоставить `param` фактический адрес человека, над который вы хотите работать, например:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Это означает, что `param` вы не можете установить все поля null, как вы можете с `outputColumn` полями.

`IsFieldNullable`реализуется через [DoFieldExchange](#dofieldexchange).

## <a name="crecordsetisopen"></a><a name="isopen"></a>CRecordset::IsOpen

Определяет, если запись уже открыта.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если функция участника [Open](#open) или [Requery](#requery) объекта записи ранее была вызвана и набор записей не был закрыт; в противном случае 0.

## <a name="crecordsetm_hstmt"></a><a name="m_hstmt"></a>CRecordset::m_hstmt

Содержит ручку к структуре данных оператора ODBC, типа HSTMT, связанную с рекордным набором.

### <a name="remarks"></a>Remarks

Каждый запрос к источнику данных ODBC связан с HSTMT.

> [!CAUTION]
> Не используйте `m_hstmt` до вызова [Open.](#open)

Обычно вам не нужно получать напрямую доступ к HSTMT, но он может понадобиться для прямого выполнения инструкций по S'L. Функция `ExecuteSQL` члена класса `CDatabase` приводит пример `m_hstmt`использования .

## <a name="crecordsetm_nfields"></a><a name="m_nfields"></a>CRecordset::m_nFields

Содержит количество полевых данных в классе recordset; т.е. количество столбцов, выбранных рекордным набором из источника данных.

### <a name="remarks"></a>Remarks

Конструктор для класса recordset должен `m_nFields` инициализировать с правильным числом. Если вы не реализовали объемстроки извлечения, ClassWizard пишет эту инициализацию для вас, когда вы используете его, чтобы объявить свой класс рекордсета. Вы также можете написать его вручную.

Платформа использует это число для управления взаимодействием между членами данных на местах и соответствующими столбцов текущей записи источника данных.

> [!CAUTION]
> Этот номер должен соответствовать количеству "выходных `DoFieldExchange` `DoBulkFieldExchange` столбцов", зарегистрированных в `CFieldExchange::outputColumn`SetFieldType или после вызова в [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) с параметром.

Можно динамически связывать столбцы, как поясняется в статье "Запись: динамически связывающие столбцы данных". Если вы это сделаете, необходимо `m_nFields` увеличить количество голосов, чтобы отразить количество вызовов функции RFX или Bulk RFX в вашей `DoFieldExchange` функции или `DoBulkFieldExchange` функции участника для динамически связанных столбцов.

Для получения дополнительной информации смотрите статьи [Recordset: Динамически связывающие колонки данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) и [Recordset: Извлечение записей в массовых (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

Смотрите статью [Запись Поле обмена: Использование RFX](../../data/odbc/record-field-exchange-using-rfx.md).

## <a name="crecordsetm_nparams"></a><a name="m_nparams"></a>CRecordset::m_nParams

Содержит количество параметров данных членов в классе recordset; то есть количество параметров, пройдено с запросом рекорда.

### <a name="remarks"></a>Remarks

Если в классе записей есть какие-либо параметры данных, `m_nParams` конструктор для класса должен инициализировать сятное число. Значение `m_nParams` по умолчанию до 0. Если вы добавляете параметры данных (что вы должны делать вручную), вы также должны вручную добавить инициализацию в конструкторе класса, чтобы `m_strFilter` отразить `m_strSort` количество параметров (которые должны быть по крайней мере, как большой, как число "заполнителей в вашей или строки").

Платформа использует это число, когда параметризирует запрос набора записей.

> [!CAUTION]
> Этот номер должен соответствовать номеру `DoFieldExchange` «парамов», зарегистрированным в [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) `CFieldExchange::inputParam`или `CFieldExchange::param` `DoBulkFieldExchange` `CFieldExchange::outputParam`после его звонка с параметрическим значением, или `CFieldExchange::inoutParam`.

### <a name="example"></a>Пример

  Смотрите статьи [Recordset: Параметризация рекордсета (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) и [биржа поля записи: Использование RFX](../../data/odbc/record-field-exchange-using-rfx.md).

## <a name="crecordsetm_pdatabase"></a><a name="m_pdatabase"></a>CRecordset::m_pDatabase

Содержит указатель на `CDatabase` объект, через который запись подключена к источнику данных.

### <a name="remarks"></a>Remarks

Эта переменная устанавливается двумя способами. Как правило, при построении `CDatabase` объекта записи указатель передается на уже подключенный объект. Если вы передаете `CRecordset` NULL `CDatabase` вместо этого, создает объект для вас и соединяет его. В любом `CRecordset` случае хранит указатель в этой переменной.

Обычно вам не нужно будет напрямую `m_pDatabase`использовать указатель, хранящийся в. Если вы пишете свои `CRecordset`собственные расширения, однако, возможно, потребуется использовать указатель. Например, вам может понадобиться указатель, `CDBException`если вы бросаете свой собственный s. Или это может понадобиться, если вам `CDatabase` нужно сделать что-то с помощью одного `ExecuteSQL` и того `CDatabase` же объекта, например, для выполнения транзакций, настройки тайм-аутов или вызова функции участника класса для непосредственного выполнения инструкций S'L.

## <a name="crecordsetm_strfilter"></a><a name="m_strfilter"></a>CRecordset::m_strFilter

После построения объекта записи, но `Open` прежде чем вы позвоните `CString` в функцию его члена, используйте этот член данных для хранения содержащего оговорку S'L **WHERE.**

### <a name="remarks"></a>Remarks

Запись использует эту строку для ограничения (или фильтрации) `Open` `Requery` записей, выбранных во время вызова или вызова. Это полезно для выбора подмножества записей, таких как "все продавцы, базирующиеся в Калифорнии" ("государство и CA"). Синтаксис ODBC S'L для оговорки **WHERE**

`WHERE search-condition`

Обратите внимание, что вы не включаете ключевое слово **WHERE** в строку. Рамки поставляют его.

Вы также можете параметризировать строку фильтра, разместив в ней заполнителей параметра, объявив в своем классе участника параметра для каждого заполнителя и передав параметры к рекорду во время выполнения. Это позволяет построить фильтр во время выполнения. Для получения дополнительной информации, [см.](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md)

Для получения более подробной информации о [SQL](../../data/odbc/sql.md)положениях S'L **WHERE,** см. Для получения дополнительной информации о выборе [Recordset: Filtering Records (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md)и фильтрации записей, см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]

## <a name="crecordsetm_strsort"></a><a name="m_strsort"></a>CRecordset::m_strSort

После построения объекта записи, но `Open` прежде чем вы позвоните `CString` в функцию его члена, используйте этот член данных для хранения содержащего оговорку S'L **ORDER BY.**

### <a name="remarks"></a>Remarks

Запись использует эту строку для сортировки `Open` `Requery` записей, выбранных во время вызова или вызова. Эту функцию можно использовать для сортировки набора записей на одном или нескольких столбцах. Синтаксис ODBC S'L для оговорки **ORDER BY**

`ORDER BY sort-specification [, sort-specification]...`

где сортировока — это ряд или название столбца. Вы также можете указать восходящий или убывающий порядок (порядок поднимается по умолчанию) путем приписанивания "ASC" или "DESC" к списку столбцов в строке сортировки. Выбранные записи сортируются сначала по первой указанной колонке, затем по второй и так далее. Например, можно заказать запись "Клиенты", установленную по фамилии, а затем по имени. Количество столбцов, которые можно перечислить, зависит от источника данных. Для получения дополнительной информации см.

Обратите внимание, что в строку не включено ключевое слово **ORDER BY.** Рамки поставляют его.

Для получения более подробной информации [SQL](../../data/odbc/sql.md)о положениях, которые есть в s'L, см. Для получения дополнительной информации о [Recordset: Sorting Records (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md)сортировке записей, см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]

## <a name="crecordsetmove"></a><a name="move"></a>CRecordset::Перемещение

Перемещает текущий указатель рекорда в пределах набора рекордов, либо вперед, либо назад.

```
virtual void Move(
    long nRows,
    WORD wFetchType = SQL_FETCH_RELATIVE);
```

### <a name="parameters"></a>Параметры

*nRows*<br/>
Количество строк для перемещения вперед или назад. Положительные значения движутся вперед, к концу рекорда. Отрицательные значения движутся назад, к началу.

*wFetchType*<br/>
Определяет набор строк, `Move` который будет получать. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Remarks

Если вы передаете значение 0 для `Move` *nRows,* обновляет текущую запись; `Move` закончится любым `AddNew` `Edit` течением или режимом и восстановит `AddNew` значение `Edit` текущей записи до или было вызвано.

> [!NOTE]
> При перемещении через рекордный установить нельзя пропустить удаленные записи. Смотрите [CRecordset::IsDeleted](#isdeleted) для получения дополнительной информации. При открытии `CRecordset` `skipDeletedRecords` параметра опционов утверждается, `Move` что параметр *nRows* равен 0. Такое поведение предотвращает обновление строк, удаленных другими клиентскими приложениями с использованием тех же данных. Смотрите параметр *dwOption* в [Open](#open) для описания `skipDeletedRecords`.

`Move`переопределяет рекорд, установленный рядами. Основываясь на значениях для *nRows* `Move` и *wFetchType,* получает соответствующий набор строк, а затем делает первую запись в этом строке текущей записи. Если вы не реализовали объем строки извлечения, то размер строки всегда 1. При получении строки, `Move` непосредственно вызывает функцию участника [CheckRowsetError](#checkrowseterror) для обработки любых ошибок, возникающих в результате получения.

В зависимости от значений, которые вы передаете, `Move` эквивалентно другим `CRecordset` функциям члена. В частности, значение *wFetchType* может указывать на функцию члена, которая является более интуитивной и часто предпочтительным методом перемещения текущей записи.

В следующей таблице перечислены возможные значения для `Move` *wFetchType*, набор строк, который будет получать на основе *wFetchType* и *nRows,* и любой эквивалентной функции члена, соответствующей *wFetchType.*

|wFetchType|Извлеченный ряд|Эквивалентная функция члена|
|----------------|--------------------|--------------------------------|
|SQL_FETCH_RELATIVE (значение по умолчанию)|Строка, начинающаяся *nRows строки* (ы) из первого ряда в текущем строке.||
|SQL_FETCH_NEXT|Следующий ряд; *nRows* игнорируется.|[MoveNext](#movenext)|
|SQL_FETCH_PRIOR|Предыдущая строка; *nRows* игнорируется.|[MovePrev](#moveprev)|
|SQL_FETCH_FIRST|Первый ряд в рекорде; *nRows* игнорируется.|[MoveFirst](#movefirst)|
|SQL_FETCH_LAST|Последний полный ряд в рекордном наборе; *nRows* игнорируется.|[MoveLast](#movelast)|
|SQL_FETCH_ABSOLUTE|Если *nRows* > 0, строка, начинающая сярвые *строки (ы)* с начала рекорда. Если *nRows* < 0, строка, начиная *nRows строки* (ы) с конца рекорда. Если *nRows* 0, то состояние начала файла (BOF) возвращается.|[SetAbsolutePosition](#setabsoluteposition)|
|SQL_FETCH_BOOKMARK|Строка, начинаюая сяпом, начинается с строки, значение закладки которого соответствует *nRows.*|[SetBookmark](#setbookmark)|

> [!NOTE]
> Для записей только `Move` вперед, действителен только со значением SQL_FETCH_NEXT для *wFetchType*.

> [!CAUTION]
> Вызов `Move` бросает исключение, если в наборе записей нет записей. Чтобы определить, есть ли записи, позвоните [isBOF](#isbof) и [IsEOF](#iseof).

> [!NOTE]
> Если вы прокрутили мимо начала или конца`IsBOF` `IsEOF` рекорда (или `Move` возвращается ненулевой), вызов функции, возможно, бросить `CDBException`. Например, `IsEOF` если возвращается `IsBOF` ненулевой `MoveNext` и нет, `MovePrev` то будет бросать исключение, но не будет.

> [!NOTE]
> Если вы `Move` звоните во время обновления или добавления текущей записи, обновления теряются без предупреждения.

Для получения дополнительной информации о навигации recordset, см. [Recordset: Bookmarks and Absolute Positions (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Для получения соответствующей `SQLExtendedFetch` информации см.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]

## <a name="crecordsetmovefirst"></a><a name="movefirst"></a>CRecordset::MoveFirst

Делает первую запись в первом ряду, устанавливая текущую запись.

```
void MoveFirst();
```

### <a name="remarks"></a>Remarks

Независимо от того, была ли реализована основная строка, это всегда будет первой записью в рекорде.

Вам не нужно `MoveFirst` звонить сразу после открытия набора записей. В это время первая запись (если таковая имеется) автоматически является текущей записью.

> [!NOTE]
> Эта функция участника не действительна для записей только для форвардов.

> [!NOTE]
> При перемещении через рекордный установить нельзя пропустить удаленные записи. Подробнее о функции [IsDeleted.](#isdeleted)

> [!CAUTION]
> Вызов любой `Move` из функций выбрасывает исключение, если в наборе записей нет записей. Чтобы определить, есть ли записи, вызов `IsBOF` и `IsEOF`.

> [!NOTE]
> Если вы называете `Move` какие-либо функции во время обновления или добавления текущей записи, обновления теряются без предупреждения.

Для получения дополнительной информации о навигации recordset, см. [Recordset: Bookmarks and Absolute Positions (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  Смотрите пример [IsBOF](#isbof).

## <a name="crecordsetmovelast"></a><a name="movelast"></a>CRecordset::MoveLast

Делает первую запись в последнем полном ряде текущей записи.

```
void MoveLast();
```

### <a name="remarks"></a>Remarks

Если вы не реализовали объем строки извлечения, ваш рекорд `MoveLast` имеет размер строки 1, так что просто движется к последней записи в recordset.

> [!NOTE]
> Эта функция участника не действительна для записей только для форвардов.

> [!NOTE]
> При перемещении через рекордный установить нельзя пропустить удаленные записи. Подробнее о функции [IsDeleted.](#isdeleted)

> [!CAUTION]
> Вызов любой `Move` из функций выбрасывает исключение, если в наборе записей нет записей. Чтобы определить, есть ли записи, вызов `IsBOF` и `IsEOF`.

> [!NOTE]
> Если вы называете `Move` какие-либо функции во время обновления или добавления текущей записи, обновления теряются без предупреждения.

Для получения дополнительной информации о навигации recordset, см. [Recordset: Bookmarks and Absolute Positions (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  Смотрите пример [IsBOF](#isbof).

## <a name="crecordsetmovenext"></a><a name="movenext"></a>CRecordset::MoveNext

Делает первую запись в следующем строке, устанавливая текущую запись.

```
void MoveNext();
```

### <a name="remarks"></a>Remarks

Если вы не реализовали объем строки извлечения, ваш рекорд `MoveNext` имеет размер строки 1, так что просто переходит к следующей записи.

> [!NOTE]
> При перемещении через рекордный установить нельзя пропустить удаленные записи. Подробнее о функции [IsDeleted.](#isdeleted)

> [!CAUTION]
> Вызов любой `Move` из функций выбрасывает исключение, если в наборе записей нет записей. Чтобы определить, есть ли записи, вызов `IsBOF` и `IsEOF`.

> [!NOTE]
> Также рекомендуется звонить `IsEOF` перед вызовом. `MoveNext` Например, если вы прокрутили мимо конца `IsEOF` рекорда, вернется ненулевой; последующий вызов `MoveNext` будет бросать исключение.

> [!NOTE]
> Если вы называете `Move` какие-либо функции во время обновления или добавления текущей записи, обновления теряются без предупреждения.

Для получения дополнительной информации о навигации recordset, см. [Recordset: Bookmarks and Absolute Positions (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  Смотрите пример [IsBOF](#isbof).

## <a name="crecordsetmoveprev"></a><a name="moveprev"></a>CRecordset::MovePrev

Делает первую запись в предыдущем строке, установленной текущей записью.

```
void MovePrev();
```

### <a name="remarks"></a>Remarks

Если вы не реализовали объем строки извлечения, ваш рекорд `MovePrev` имеет размер строки 1, так что просто переходит к предыдущей записи.

> [!NOTE]
> Эта функция участника не действительна для записей только для форвардов.

> [!NOTE]
> При перемещении через рекордный установить нельзя пропустить удаленные записи. Подробнее о функции [IsDeleted.](#isdeleted)

> [!CAUTION]
> Вызов любой `Move` из функций выбрасывает исключение, если в наборе записей нет записей. Чтобы определить, есть ли записи, вызов `IsBOF` и `IsEOF`.

> [!NOTE]
> Также рекомендуется звонить `IsBOF` перед вызовом. `MovePrev` Например, если вы прокрутили впереди начала `IsBOF` набора рекордов, вернется ненулевой; последующий вызов `MovePrev` будет бросать исключение.

> [!NOTE]
> Если вы называете `Move` какие-либо функции во время обновления или добавления текущей записи, обновления теряются без предупреждения.

Для получения дополнительной информации о навигации recordset, см. [Recordset: Bookmarks and Absolute Positions (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  Смотрите пример [IsBOF](#isbof).

## <a name="crecordsetonsetoptions"></a><a name="onsetoptions"></a>CRecordset::OnsetOptions

Вызывается для набора параметров (используется при выборе) для указанной выписки ODBC.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Параметры

*hstmt*<br/>
HSTMT заявления ODBC, варианты которого должны быть установлены.

### <a name="remarks"></a>Remarks

Вызов `OnSetOptions` для установки опций (используется при выборе) для указанной выписки ODBC. Платформа вызывает эту функцию члена для установки первоначальных вариантов для набора записей. `OnSetOptions`определяет поддержку источника данных для прокрутки курсоров и для параллелизма курсора и устанавливает параметры рекорда соответственно. (В `OnSetOptions` то время как `OnSetUpdateOptions` используется для операций отбора, используется для операций обновления.)

Переопределение `OnSetOptions` для установки параметров, специфиченных для драйвера или источника данных. Например, если ваш источник данных поддерживает открытие `OnSetOptions` для эксклюзивного доступа, можно переопределить, чтобы воспользоваться этой возможностью.

Для получения дополнительной информации о курсорах, смотрите в статье [ODBC](../../data/odbc/odbc-basics.md).

## <a name="crecordsetonsetupdateoptions"></a><a name="onsetupdateoptions"></a>CRecordset::OnSetUpdateOptions

Вызывается для установки параметров (используется в обновлении) для указанной выписки ODBC.

```
virtual void OnSetUpdateOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Параметры

*hstmt*<br/>
HSTMT заявления ODBC, варианты которого должны быть установлены.

### <a name="remarks"></a>Remarks

Вызов `OnSetUpdateOptions` для установки опций (используется в обновлении) для указанной выписки ODBC. Платформа вызывает эту функцию участника после создания HSTMT для обновления записей в рекордном наборе. (В `OnSetOptions` то время как `OnSetUpdateOptions` используется для операций отбора, используется для операций обновления.) `OnSetUpdateOptions` определяет поддержку источника данных для прокрутки курсоров и для параллелизма курсора и устанавливает параметры рекорда соответственно.

Переопределение `OnSetUpdateOptions` для установки параметров оператора ODBC до того, как это заявление будет использовано для доступа к базе данных.

Для получения дополнительной информации о курсорах, смотрите в статье [ODBC](../../data/odbc/odbc-basics.md).

## <a name="crecordsetopen"></a><a name="open"></a>CRecordset::Открыто

Открывает запись, извлекая таблицу или выполняя запрос, который представляет собой набор записей.

```
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    DWORD dwOptions = none);
```

### <a name="parameters"></a>Параметры

*nOpenType*<br/>
Примите значение по умолчанию, AFX_DB_USE_DEFAULT_TYPE или используйте `enum OpenType`одно из следующих значений из:

- `CRecordset::dynaset`Рекордс с двунаправленной прокруткой. Членство и порядок записей определяются при открытии набора записей, но изменения, внесенные другими пользователями в значения данных, видны после операции по извлечению. Dynasets также известны как набор ы ключей управляемых рекордсетов.

- `CRecordset::snapshot`Статический рекорд с двунаправленной прокруткой. Членство и порядок записей определяются при открытии регистрации; значения данных определяются при извлечении записей. Изменения, внесенные другими пользователями, не видны до тех пор, пока запись не будет закрыта, а затем вновь открыта.

- `CRecordset::dynamic`Рекордс с двунаправленной прокруткой. Изменения, внесенные другими пользователями в значения членства, заказа и данных, видны после операции по извлечению. Обратите внимание, что многие драйверы ODBC не поддерживают этот тип рекорда.

- `CRecordset::forwardOnly`Запись только для чтения только с перенасежкой.

   Для, `CRecordset`значение по `CRecordset::snapshot`умолчанию . Механизм значения по умолчанию позволяет мастерам Visual C's `CRecordset` взаимодействовать `CDaoRecordset`как с ODBC, так и с DAO, которые имеют различные по умолчанию.

Для получения дополнительной информации об этих [Recordset (ODBC)](../../data/odbc/recordset-odbc.md)типах рекордов см. Для получения соответствующей информации смотрите статью "Использование блокируемых и прокрутки курсоров" в SDK Windows.

> [!CAUTION]
> Если запрашиваемый тип не поддерживается, фреймворк выбрасывает исключение.

*lpszS'L*<br/>
Строка указатель, содержащий один из следующих:

- Указатель NULL.

- Имя таблицы.

- Заявление S'L **SELECT** (по желанию с оговоркой S'L **WHERE** или **ORDER BY).**

- Заявление **CALL** с указанием имени заданного запроса (процедура хранения). Будьте осторожны, что вы не вставить пробел между фигурные скобки и ключевое слово **CALL.**

Для получения дополнительной информации об этой строке смотрите таблицу и обсуждение роли ClassWizard в разделе [Замечания.](#remarks)

> [!NOTE]
> Порядок столбцов в наборе результатов должен соответствовать порядку вызовов функции RFX или Bulk RFX в функции [DoFieldExchange](#dofieldexchange) или [DoBulkFieldExchange.](#dobulkfieldexchange)

*dwOptions*<br/>
Битовая маска, которая может указать комбинацию значений, перечисленных ниже. Некоторые из них являются взаимоисключающими. Значение по умолчанию **не**является .

- `CRecordset::none`Параметры не установлены. Значение этого параметра является взаимоисключающим со всеми другими значениями. По умолчанию, рекордсет может быть обновлен с [помощью Edit](#edit) или [Удалить](#delete) и позволяет добавлять новые записи с [AddNew](#addnew). Updatability зависит от источника данных, а также от указанного вами варианта *nOpenType.* Оптимизация для оптовых добавок недоступна. Массовая строка извлечения не будет реализована. Удаленные записи не будут пропущены во время навигации recordset. Закладки недоступны. Осуществляется автоматическая проверка грязного поля.

- `CRecordset::appendOnly`Не допускайте `Edit` или `Delete` на рекорд. Разрешить `AddNew` только. Эта опция является `CRecordset::readOnly`взаимоисключающим с .

- `CRecordset::readOnly`Откройте рекорд как только для чтения. Эта опция является `CRecordset::appendOnly`взаимоисключающим с .

- `CRecordset::optimizeBulkAdd`Используйте подготовленную выписку по S'L для оптимизации добавления многих записей одновременно. Применяется только в том случае, если `SQLSetPos` вы не используете функцию ODBC API для обновления набора записей. Первое обновление определяет, какие поля помечены как грязные. Эта опция является `CRecordset::useMultiRowFetch`взаимоисключающим с .

- `CRecordset::useMultiRowFetch`Реализация объемного строки, извлеченной, чтобы можно было получить несколько строк в одной операции по извлечению. Это расширенная функция, предназначенная для повышения производительности; однако, обмен поля миссоциы не поддерживается ClassWizard. Эта опция является `CRecordset::optimizeBulkAdd`взаимоисключающим с . Обратите внимание, `CRecordset::useMultiRowFetch`что если `CRecordset::noDirtyFieldCheck` вы укажете, то опция будет включена автоматически (двойной буферизация не будет доступна); на передних записях `CRecordset::useExtendedFetch` опцион будет включен автоматически. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

- `CRecordset::skipDeletedRecords`Пропустить все удаленные записи при навигации по рекорду. Это замедлит производительность в некоторых относительных извлечений. Этот параметр не действителен только на передних записях. Если вы называете [Перемещение](#move) с параметром *nRows,* установленным до 0, и набором `CRecordset::skipDeletedRecords` опционов, `Move` будет утверждать. Обратите `CRecordset::skipDeletedRecords` внимание, что это похоже на *упаковку драйвера,* что означает, что удаленные строки удаляются из набора записей. Однако, если ваш драйвер упаковывает записи, то он пропустит только те записи, которые вы удаляете; он не пропустит записи, удаленные другими пользователями, пока запись открыта. `CRecordset::skipDeletedRecords`будет пропускать строки, удаленные другими пользователями.

- `CRecordset::useBookmarks`Может использовать закладки на рекорде, если поддерживается. Закладки замедляют поиск данных, но повышают производительность навигации данных. Не действителен только на передних рекордах. Для получения дополнительной информации, смотрите статью [Recordset: Закладки и Абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

- `CRecordset::noDirtyFieldCheck`Выключите автоматическую проверку грязного поля (двойной буферизации). Это позволит повысить производительность; однако, вы должны вручную пометить `SetFieldDirty` `SetFieldNull` поля как грязные, вызывая и функции члена. Обратите внимание, что `CRecordset` двойное буферизация в `CDaoRecordset`классе аналогична двойной буферизации в классе. Однако `CRecordset`в , вы не можете включить двойное буферизации на отдельных полях; вы либо включите его для всех полей, либо отключите его для всех полей. Обратите внимание, что `CRecordset::useMultiRowFetch`если `CRecordset::noDirtyFieldCheck` вы укажете опцию, то будет включен автоматически; `SetFieldDirty` однако, `SetFieldNull` и не может быть использован на рекордных наборах, которые реализуют объемстроки извлечения.

- `CRecordset::executeDirect`Не используйте подготовленную выписку по S'L. Для повышения производительности укажите `Requery` этот параметр, если функция участника никогда не будет вызываться.

- `CRecordset::useExtendedFetch`Реализация `SQLExtendedFetch` вместо `SQLFetch`. Это предназначено для реализации объемных строк, извлеченных на передних записях. Если вы укажете опцию `CRecordset::useMultiRowFetch` на форвард-только рекорд, то `CRecordset::useExtendedFetch` будет включен автоматически.

- `CRecordset::userAllocMultiRowBuffers`Пользователь будет выделять буферы хранения для данных. Используйте эту опцию в сочетании с, `CRecordset::useMultiRowFetch` если вы хотите выделить свой собственный хранения; в противном случае фреймворк автоматически распределит необходимое хранилище. Для получения дополнительной информации, [см.](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md) Обратите внимание, `CRecordset::userAllocMultiRowBuffers` что `CRecordset::useMultiRowFetch` указание без указания приведет к неудавому утверждению.

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `CRecordset` если объект был успешно открыт; в противном случае 0, если [CDatabase:: Открыть](../../mfc/reference/cdatabase-class.md#open) (если называется) возвращает 0.

### <a name="remarks"></a>Remarks

Необходимо вызвать эту функцию участника для выполнения запроса, определяемого рекордным набором. Перед `Open`вызовом необходимо построить объект, установленный записью.

Подключение этого набора записей к источнику данных зависит от `Open`того, как вы строите запись перед вызовом. Если вы передаете объект [CDatabase](../../mfc/reference/cdatabase-class.md) конструктору, который не был подключен к источнику данных, эта функция-член использует [GetDefaultConnect](#getdefaultconnect) для попытки открыть объект базы данных. Если вы передаете NULL конструктору, конструктор строит `CDatabase` объект для вас `Open` и пытается подключить объект базы данных. Для получения подробной информации о закрытии рекорда и связи при этих различных обстоятельствах, [см.](#close)

> [!NOTE]
> Доступ к источнику `CRecordset` данных через объект всегда используется. В `CDaoRecordset` отличие от класса, `CRecordset` вы не можете использовать объект для открытия источника данных с эксклюзивным доступом.

При вызове `Open`запроса, обычно оператора S'L **SELECT,** выбирает записи на основе критериев, показанных в следующей таблице.

|Значение параметра lpszS'L|Выбранные записи определяются|Пример|
|------------------------------------|----------------------------------------|-------------|
|NULL|Строка возвращается . `GetDefaultSQL`||
|Название таблицы S'L|Все столбцы таблицы-лист `DoFieldExchange` `DoBulkFieldExchange`ам-листа в или .|`"Customer"`|
|Предопределенное имя запроса (процедура хранения)|Столбики запроса определены для возврата.|`"{call OverDueAccts}"`|
|**Выберите** список столбцов **из** списка таблиц|Указанные столбцы из указанной таблицы (ы).|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|

> [!CAUTION]
> Будьте осторожны, что вы не вставляете дополнительное пробелв в строку S'L. Например, если вы вставите пробел между фигурной скобкой и ключевым словом **CALL,** MFC неправильно истолкует строку S'L как название таблицы и включит ее в заявление **SELECT,** что приведет к тому, что исключение будет брошено. Аналогичным образом, если ваш предопределенный запрос использует параметр вывода, не вставляйте пробел между фигурной скобкой и символом ''. Наконец, вы не должны вставлять пробел перед фигурной скобкой в заявлении **CALL** или перед ключевым словом **SELECT** в заявлении **SELECT.**

Обычная процедура заключается `Open`в том, чтобы пройти NULL к ; в этом `Open` случае, вызывает [GetDefaultS'L](#getdefaultsql). Если вы используете `CRecordset` производный класс, `GetDefaultSQL` указано название таблицы (ы), указанное в ClassWizard. Вместо этого можно указать `lpszSQL` другую информацию в параметре.

Что бы `Open` вы ни прошли, конструируется окончательная строка S'L для запроса `lpszSQL` (строка может иметь положения S'L **WHERE** и **ORDER BY,** приложенные к строке, которую вы прошли), а затем выполняет запрос. Вы можете изучить построенную строку, `Open`позвонив [getS'L](#getsql) после вызова . Для получения дополнительной информации о том, как запись строит заявление s'L и выбирает записи, см. [Recordset: How Recordsets Select Records (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)

Члены полевых данных класса записей привязаны к выбранным столбцов. При возврате каких-либо записей первая запись становится текущей записью.

Если требуется установить параметры для набора записей, например фильтр или сортировку, `Open`укажите их после построения объекта записи, но перед вызовом. Если вы хотите обновить записи в записи после того, как запись уже открыта, позвоните [в Requery](#requery).

Для получения дополнительной информации, в ключая дополнительные примеры, см. Статьи [Recordset (ODBC)](../../data/odbc/recordset-odbc.md), [Запись: Как записи Выберите записи (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md), и [Recordset: Создание и закрытие записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

### <a name="example"></a>Пример

Следующие примеры кода отображали различные `Open` формы вызова.

[!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]

## <a name="crecordsetrefreshrowset"></a><a name="refreshrowset"></a>CRecordset::RefreshRowset

Обновляет данные и состояние строки в текущем наборе строк.

```
void RefreshRowset(
    WORD wRow,
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Параметры

*wRow*<br/>
Одноразовая позиция строки в текущем ряде. Это значение может варьироваться от нуля до размера строки.

*wLockType*<br/>
Значение, указывающее, как заблокировать строку после его обновления. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Remarks

Если вы пройдете значение ноль для *wRow,* то каждый ряд в rowset будет обновлен.

Для `RefreshRowset`использования необходимо реализовать объемный ряд, указав опцию `CRecordset::useMulitRowFetch` в функции члена [Open.](#open)

`RefreshRowset`вызывает функцию `SQLSetPos`API ODBC. Параметр *wLockType* определяет состояние блокировки строки `SQLSetPos` после выполнения. В следующей таблице описаны возможные значения для *wLockType*.

|wLockType|Описание|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (значение по умолчанию)|Драйвер или источник данных гарантирует, что строка находится в том `RefreshRowset` же заблокированном или разблокированном состоянии, как это было раньше.|
|SQL_LOCK_EXCLUSIVE|Драйвер или источник данных блокирует строку исключительно. Не все источники данных поддерживают этот тип блокировки.|
|SQL_LOCK_UNLOCK|Водитель или источник данных разблокирует строку. Не все источники данных поддерживают этот тип блокировки.|

Для получения `SQLSetPos`дополнительной информации о , см. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetrequery"></a><a name="requery"></a>CRecordset::Requery

Перестраивает (обновляет) рекорд.

```
virtual BOOL Requery();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если рекорд был успешно восстановлен; в противном случае 0.

### <a name="remarks"></a>Remarks

При возврате каких-либо записей первая запись становится текущей записью.

Для того, чтобы запись отражала дополнения и удаления, которые вы или другие пользователи вносите в исходный исход данных, необходимо восстановить набор записей, позвонив в систему. `Requery` Если запись — это динасет, он автоматически отражает обновления, которые вы или другие пользователи вносили в существующие записи (но не дополнения). Если запись представляет собой моментальный `Requery` снимок, необходимо позвонить, чтобы отразить edits другими пользователями, а также дополнения и удаления.

Для динасета или снимка `Requery` звоните в любое время, когда вы хотите восстановить запись с помощью нового фильтра или сортировки, или новых значений параметров. Установите новый фильтр или сортируйте `m_strFilter` свойство, назначив новые значения и `m_strSort` до вызова. `Requery` Установите новые параметры, назначив новые значения `Requery`членам параметров, прежде чем вызывать. Если строки фильтра и сортировки не изменились, можно повторно использовать запрос, что повышает производительность.

Если попытка восстановить набор записей завершается неудачей, запись закрывается. Перед вызовом `Requery`можно определить, можно ли перезадействовать запись, позвонив в функцию `CanRestart` участника. `CanRestart`не гарантирует, `Requery` что это удастся.

> [!CAUTION]
> Звоните `Requery` только после того, как вы позвонили [Открыть](#open).

### <a name="example"></a>Пример

Этот пример восстанавливает набор записей для применения другого порядка сортировки.

[!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]

## <a name="crecordsetsetabsoluteposition"></a><a name="setabsoluteposition"></a>CRecordset::SetAbsolutePosition

Позиции рекорда на рекорде, соответствующие указанному рекордному числу.

```
void SetAbsolutePosition(long nRows);
```

### <a name="parameters"></a>Параметры

*nRows*<br/>
Одноразовая ординальное положение для текущего рекорда в рекорде.

### <a name="remarks"></a>Remarks

`SetAbsolutePosition`перемещает текущий указатель рекорда на основе этого обданного положения.

> [!NOTE]
> Эта функция участника не действительна только на передних записях.

Для рекордов ODBC абсолютная позиция 1 относится к первому рекорду в рекорде; параметр 0 относится к позиции начала файла (BOF).

Вы также можете передать `SetAbsolutePosition`отрицательные значения . В этом случае позиция рекорда оценивается с конца рекорда. Например, `SetAbsolutePosition( -1 )` перемещает текущий указатель записи к последней записи в рекордном сете.

> [!NOTE]
> Абсолютная позиция не предназначена для использования в качестве суррогатного рекордного числа. Закладки по-прежнему являются рекомендуемым способом сохранения и возвращения в заданную позицию, так как позиция записи меняется при удалении предыдущих записей. Кроме того, вы не можете быть уверены в том, что данная запись будет иметь ту же абсолютную позицию, если запись будет повторно создана, поскольку порядок отдельных записей в рекордном наборе не гарантируется, если он не создан с помощью оператора S'L с использованием оговорки **ORDER BY.**

Для получения дополнительной информации о навигации и закладках, см. [Recordset: Bookmarks and Absolute Positions (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) [Recordset: Scrolling (ODBC)](../../data/odbc/recordset-scrolling-odbc.md)

## <a name="crecordsetsetbookmark"></a><a name="setbookmark"></a>CRecordset::SetBookmark

Позиции рекорда на запись, содержащую указанную закладку.

```
void SetBookmark(const CDBVariant& varBookmark);
```

### <a name="parameters"></a>Параметры

*varBookmark*<br/>
Ссылка на объект [CDBVariant,](../../mfc/reference/cdbvariant-class.md) содержащий значение закладки для конкретной записи.

### <a name="remarks"></a>Remarks

Чтобы определить, поддерживаются ли закладки на рекорде, позвоните [в CanBookmark](#canbookmark). Чтобы сделать закладки доступными, `CRecordset::useBookmarks` если они поддерживаются, необходимо установить опцию в параметре *dwOptions* функции [Open](#open) member.

> [!NOTE]
> Если закладки не поддерживаются `SetBookmark` или недоступны, вызов приведет к тому, что исключение будет брошено. Закладки не поддерживаются на форвардных записях.

Чтобы сначала получить закладку для текущей записи, позвоните [GetBookmark](#getbookmark) `CDBVariant` , который сохраняет значение закладки для объекта. Позже вы можете вернуться `SetBookmark` к этой записи, позвонив по сохраненному значению закладки.

> [!NOTE]
> После определенных операций записи, вы должны `SetBookmark`проверить настойчивость закладки перед вызовом . Например, если вы извлекнете `GetBookmark` закладку, а затем позвоните, `Requery`закладка может быть недействительной. Позвоните [CDatabase::GetBookmarkPersistenceenceenceenceenceence,](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) чтобы проверить, можете ли вы безопасно позвонить `SetBookmark`.

Для получения дополнительной информации о закладках и навигации, смотрите статьи [Recordset: Закладки и Абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [Рекордсет: Прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

## <a name="crecordsetsetfielddirty"></a><a name="setfielddirty"></a>CRecordset::SetFieldDirty

Флаги полевых данных, являваемые членами рекорда, изменены или неизменены.

```
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
Содержит адрес члена полевых данных в наборе записей или NULL. Если NULL, все полевых данных в наборе записей помечены. (СЗ НУЛТ не то же самое, что Null в терминологии базы данных, что означает "не имеет значения.")

*bDirty*<br/>
ПРАВДА, если член данных поля должен быть помечен как "грязный" (изменен). В противном случае FALSE, если член данных полевого поля должен быть помечен как "чистый" (без изменений).

### <a name="remarks"></a>Remarks

Маркировка полей как неизменная гарантирует, что поле не обновляется и приводит к меньшему трафику S'L.

> [!NOTE]
> Эта функция члена не применима к рекордным наборам, использующим извлечения объемных строк. Если вы реализовали объем строки извлечения, то `SetFieldDirty` приведет к неудалось утверждение. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Рамочные знаки изменили членов полевых данных, чтобы гарантировать, что они будут записаны на запись источника данных механизмом обмена полями записи (RFX). Изменение значения поля обычно автоматически устанавливает поле грязным, поэтому вам `SetFieldDirty` редко придется звонить себе, но иногда может потребоваться гарантировать, что столбцы будут явно обновлены или вставлены независимо от того, какое значение находится в составе члена данных поля.

> [!CAUTION]
> Позвоните в эту функцию участника только после того, как вы позвонили [edit](#edit) или [AddNew](#addnew).

Использование NULL для первого аргумента функции `outputColumn` будет применять `param` функцию только к полям, а не полям. Например, вызов

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

установит только `outputColumn` поля NULL; `param` поля не будут затронуты.

Для работы на `param` полях необходимо предоставить `param` фактический адрес человека, над который вы хотите работать, например:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Это означает, что `param` вы не можете установить все поля null, как вы можете с `outputColumn` полями.

## <a name="crecordsetsetfieldnull"></a><a name="setfieldnull"></a>CRecordset::SetFieldNull

Флаги полевых данных, являясь членом рекорда, как Null (конкретно не имеющий значения) или как не-Null.

```
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```

### <a name="parameters"></a>Параметры

*Pv*<br/>
Содержит адрес члена полевых данных в наборе записей или NULL. Если NULL, все полевых данных в наборе записей помечены. (СЗ НУЛТ не то же самое, что Null в терминологии базы данных, что означает "не имеет значения.")

*bNull*<br/>
Nonzero, если член данных полевого поля должен быть помечен как не имеющий значения (Null). В противном случае 0, если член данных поля должен быть помечен как не-Null.

### <a name="remarks"></a>Remarks

При добавлении новой записи в набор записей все участники полевых данных изначально устанавливаются на значение Null и помечаются как "грязные" (изменены). При извлечении записи из источника данных ее столбцы либо уже имеют значения, либо являются null.

> [!NOTE]
> Не вызывайте эту функцию участника на рекордные наборы, использующие извлечения объемных строк. Если вы реализовали объем строки извлечения, вызов `SetFieldNull` приводит к неудалось утверждение. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Если вы специально хотите назначить поле текущей записи `SetFieldNull` как не имевщее значение, позвоните с *bNull,* чтобы true пометить его как Null. Если поле ранее было помечено Null и теперь вы хотите придать ему значение, просто установите его новое значение. Вам не нужно снимать флаг `SetFieldNull`Null с . Чтобы определить, разрешено ли поле `IsFieldNullable`быть недействительным, позвоните .

> [!CAUTION]
> Позвоните в эту функцию участника только после того, как вы позвонили [edit](#edit) или [AddNew](#addnew).

Использование NULL для первого аргумента функции `outputColumn` будет применять `param` функцию только к полям, а не полям. Например, вызов

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

установит только `outputColumn` поля NULL; `param` поля не будут затронуты.

Для работы на `param` полях необходимо предоставить `param` фактический адрес человека, над который вы хотите работать, например:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Это означает, что `param` вы не можете установить все поля null, как вы можете с `outputColumn` полями.

> [!NOTE]
> При настройке параметров null `SetFieldNull` вызов до открытия набора записей приводит к утверждению. В этом случае звоните [SetParamNull](#setparamnull).

`SetFieldNull`реализуется через [DoFieldExchange](#dofieldexchange).

## <a name="crecordsetsetlockingmode"></a><a name="setlockingmode"></a>CRecordset::SetLockingMode

Устанавливает режим блокировки на «оптимистический» блокировку (по умолчанию) или «пессимистическую» блокировку. Определяет, как записи запираются для обновления.

```
void SetLockingMode(UINT nMode);
```

### <a name="parameters"></a>Параметры

*nMode*<br/>
Содержит одно из следующих `enum LockMode`значений из:

- `optimistic`Оптимистичная блокировка блокирует запись обновляется `Update`только во время вызова.

- `pessimistic`Пессимистическая блокировка блокирует запись, как `Edit` только вызывается, и `Update` держит ее взаперти до завершения вызова или перехода к новой записи.

### <a name="remarks"></a>Remarks

Позвоните в эту функцию участника, если вам нужно указать, какую из двух стратегий блокировки записей рекордсет использует для обновлений. По умолчанию режим блокировки рекорда. `optimistic` Вы можете изменить это `pessimistic` на более осторожную стратегию блокировки. Звоните `SetLockingMode` после построения и открытия объекта `Edit`регистрации, но прежде чем вы позвоните.

## <a name="crecordsetsetparamnull"></a><a name="setparamnull"></a>CRecordset::SetParamNull

Флаги параметра как Null (в частности, не имеющие значения) или как не-Null.

```
void SetParamNull(
    int nIndex,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Отсчитываемый с нуля индекс параметра.

*bNull*<br/>
Если TRUE (значение по умолчанию) параметр помечается как Null. В противном случае параметр помечается как не-Null.

### <a name="remarks"></a>Remarks

В отличие от [SetFieldNull,](#setfieldnull)вы можете позвонить, `SetParamNull` прежде чем открыть рекорд.

`SetParamNull`обычно используется с предопределенными запросами (сохраненными процедурами).

## <a name="crecordsetsetrowsetcursorposition"></a><a name="setrowsetcursorposition"></a>CRecordset::SetRowsetCursorPosition

Перемещает курсор в строку в рамках текущего набора строк.

```
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Параметры

*wRow*<br/>
Одноразовая позиция строки в текущем ряде. Это значение может варьироваться от 1 до размера строки.

*wLockType*<br/>
Значение с указанием того, как заблокировать строку после его обновления. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Remarks

При реализации навалочных строк извлечения записи извлекаются по строкам, где первой записью в извлеченном наборе строк является текущая запись. Для того, чтобы сделать еще одну запись `SetRowsetCursorPosition`в строке текущей записи, позвоните . Например, можно `SetRowsetCursorPosition` объединиться с функцией участника [GetFieldValue](#getfieldvalue) для динамического получения данных из любой записи вашего рекорда.

Для `SetRowsetCursorPosition`использования необходимо реализовать объемный ряд, указав `CRecordset::useMultiRowFetch` опцию параметра *dwOptions* в функции [open](#open) member.

`SetRowsetCursorPosition`вызывает функцию `SQLSetPos`API ODBC. Параметр *wLockType* определяет состояние блокировки строки `SQLSetPos` после выполнения. В следующей таблице описаны возможные значения для *wLockType*.

|wLockType|Описание|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (значение по умолчанию)|Драйвер или источник данных гарантирует, что строка находится в том `SetRowsetCursorPosition` же заблокированном или разблокированном состоянии, как это было раньше.|
|SQL_LOCK_EXCLUSIVE|Драйвер или источник данных блокирует строку исключительно. Не все источники данных поддерживают этот тип блокировки.|
|SQL_LOCK_UNLOCK|Водитель или источник данных разблокирует строку. Не все источники данных поддерживают этот тип блокировки.|

Для получения `SQLSetPos`дополнительной информации о , см. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetsetrowsetsize"></a><a name="setrowsetsize"></a>CRecordset::SetRowsetSize

Упоняет количество записей, которые вы хотите получить во время получения.

```
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```

### <a name="parameters"></a>Параметры

*dwNewRowsetSize*<br/>
Количество строк для получения во время данного получения.

### <a name="remarks"></a>Remarks

Эта функция виртуального члена определяет, сколько строк вы хотите получить во время одного получения при использовании объемного строки извлечения. Для реализации навалочных строк `CRecordset::useMultiRowFetch` извлечения необходимо установить опцию в параметре *dwOptions* функции [open](#open) member.

> [!NOTE]
> Вызов `SetRowsetSize` без реализации объемного строки извлечения приведет к неудалось утверждение.

Вызов `SetRowsetSize` перед `Open` вызовом, чтобы сначала установить размер строки для рекорда. Размер строки по умолчанию при реализации навалочных строк извлечения составляет 25.

> [!NOTE]
> Используйте осторожность `SetRowsetSize`при вызове . Если вы вручную выделяете хранилище данных (как указано в `CRecordset::userAllocMultiRowBuffers` опции параметра dwOptions), `Open`необходимо ли перераспределить `SetRowsetSize`эти буферы хранения после вызова, но прежде чем выполнить любую навигационную операцию курсора.

Чтобы получить текущий параметр для размера рядового набора, позвоните [GetRowsetSize.](#getrowsetsize)

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

## <a name="crecordsetupdate"></a><a name="update"></a>CRecordset::Обновление

Завершает или `AddNew` `Edit` выполняет операцию, сохраняя новые или отредактированные данные в источнике данных.

```
virtual BOOL Update();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если одна запись была успешно обновлена; в противном случае 0, если столбцы не изменились. Если записи не обновлялись или не обновлялось более одной записи, выбрасывается исключение. Исключение также выбрасывается для любого другого сбоя в исходном исходе данных.

### <a name="remarks"></a>Remarks

Вызов ими функции участника после вызова в функцию [AddNew](#addnew) или [Edit.](#edit) Этот вызов необходим для `AddNew` `Edit` завершения или операции.

> [!NOTE]
> Если вы реализовали объем строки `Update`извлечения, вы не можете вызвать . Это приведет к неудавому утверждению. Хотя `CRecordset` класс не предоставляет механизм обновления объемных строк данных, вы можете написать свои `SQLSetPos`собственные функции с помощью функции ODBC API. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`AddNew` И, `Edit` и подготовьте буфер редактирования, в котором добавленные или отредактированные данные размещаются для сохранения источника данных. `Update`сохраняет данные. Обновляются только те поля, которые отмечены или обнаружены как измененные.

Если источник данных поддерживает транзакции, можно сделать `Update` вызов (и его соответствующий `AddNew` или `Edit` колл) частью транзакции. Для получения дополнительной информации [Transaction (ODBC)](../../data/odbc/transaction-odbc.md)о транзакциях см.

> [!CAUTION]
> Если вы `Update` звоните `AddNew` без `Edit` `Update` первого `CDBException`вызова либо или , бросает . Если вы `AddNew` `Edit`звоните или, вы должны позвонить, `Update` прежде чем вызвать операцию `Move` или до закрытия либо регистрации или подключения источника данных. В противном случае изменения теряются без уведомления.

Подробнее об `Update` обработке сбоев читайте в статье [Recordset: How Recordsets Update Records (ODBC).](../../data/odbc/recordset-how-recordsets-update-records-odbc.md)

### <a name="example"></a>Пример

Смотрите статью [Транзакция: Выполнение транзакции в наборе рекордов (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Класс CRecordView](../../mfc/reference/crecordview-class.md)
