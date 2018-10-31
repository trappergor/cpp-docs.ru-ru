---
title: Класс CRecordset | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 086aaebcdc44439c45a219c7292da4aff9e13b06
ms.sourcegitcommit: a88d228480d4bb5834e985d7b3ead2760be95572
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "50203096"
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
|[CRecordset::CRecordset](#crecordset)|Создает объект `CRecordset`. Вашей производный класс должен предоставлять конструктор, который вызывает этот.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CRecordset::AddNew](#addnew)|Подготавливает для добавления новой записи. Вызовите `Update` для завершения добавления.|
|[CRecordset::CanAppend](#canappend)|Возвращает ненулевое значение, если новые записи добавляются в набор записей с помощью `AddNew` функция-член.|
|[CRecordset::CanBookmark](#canbookmark)|Возвращает ненулевое значение, если набор записей поддерживает закладки.|
|[CRecordset::Cancel](#cancel)|Отменяет асинхронную операцию или процесс из второго потока.|
|[CRecordset::CancelUpdate](#cancelupdate)|Отменяет все ожидающие обновления из-за `AddNew` или `Edit` операции.|
|[CRecordset::CanRestart](#canrestart)|Возвращает ненулевое значение, если `Requery` может вызываться для повторного запуска запроса набора записей.|
|[CRecordset::CanScroll](#canscroll)|Возвращает ненулевое значение, если можно прокручивать записи.|
|[CRecordset::CanTransact](#cantransact)|Возвращает ненулевое значение, если источник данных поддерживает транзакции.|
|[CRecordset::CanUpdate](#canupdate)|Возвращает ненулевое значение, если можно обновить набор записей (можно добавить, обновить или удалить записи).|
|[CRecordset::CheckRowsetError](#checkrowseterror)|Вызывается для обработки ошибок, возникающих при выполнении записи выборки.|
|[CRecordset::Close](#close)|Закрывает набора записей и HSTMT ODBC, связанные с ней.|
|[CRecordset::Delete](#delete)|Удаляет текущую запись из набора записей. Необходимо явно перейти к другой записи после удаления.|
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|Вызывается для обмена массового строк данных из источника данных в набор записей. Реализует блочный обмен полей записей (Bulk RFX).|
|[CRecordset::DoFieldExchange](#dofieldexchange)|Вызывается для обмена данными (в обоих направлениях) между элементами данных полей набора записей и соответствующая запись в источнике данных. Обмен полями (RFX) записей реализует.|
|[CRecordset::Edit](#edit)|Подготавливает для изменения текущей записи. Вызовите `Update` для завершения редактирования.|
|[CRecordset::FlushResultSet](#flushresultset)|Возвращает ненулевое значение, если есть еще один результат присвоено извлечь, при использовании предопределенного запроса.|
|[CRecordset::GetBookmark](#getbookmark)|Присваивает значение записи к объекту параметра.|
|[CRecordset::GetDefaultConnect](#getdefaultconnect)|Вызывается для получения строки подключения по умолчанию.|
|[CRecordset::GetDefaultSQL](#getdefaultsql)|Вызывается, чтобы получить строку SQL по умолчанию для выполнения.|
|[CRecordset::GetFieldValue](#getfieldvalue)|Возвращает значение поля в наборе записей.|
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|Возвращает количество полей в наборе записей.|
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|Возвращает сведения о полях определенных типов в наборе записей.|
|[CRecordset::GetRecordCount](#getrecordcount)|Возвращает число записей в наборе записей.|
|[CRecordset::GetRowsetSize](#getrowsetsize)|Возвращает количество записей, которые вы хотите получить во время одну операцию выборки.|
|[CRecordset::GetRowsFetched](#getrowsfetched)|Возвращает фактическое число строк, полученных во время выборки.|
|[CRecordset::GetRowStatus](#getrowstatus)|Возвращает состояние строки после выборки.|
|[CRecordset::GetSQL](#getsql)|Возвращает строку SQL, используемую для выбора записей для набора записей.|
|[CRecordset::GetStatus](#getstatus)|Возвращает состояние набора записей: индекс текущей записи и был ли получен окончательное количество записей.|
|[CRecordset::GetTableName](#gettablename)|Возвращает имя таблицы, на котором основан набор записей.|
|[CRecordset::IsBOF](#isbof)|Возвращает ненулевое значение, если набор записей позиционирует перед первой записью. Отсутствует текущая запись.|
|[CRecordset::IsDeleted](#isdeleted)|Возвращает ненулевое значение, если набор записей позиционируется в удаленной записи.|
|[CRecordset::IsEOF](#iseof)|Возвращает ненулевое значение, если набор записей позиционирует после последней записи. Отсутствует текущая запись.|
|[CRecordset::IsFieldDirty](#isfielddirty)|Возвращает ненулевое значение, если указанное поле в текущей записи был изменен.|
|[CRecordset::IsFieldNull](#isfieldnull)|Возвращает ненулевое значение, если указанное поле в текущей записи имеет значение null (не имеет значения).|
|[CRecordset::IsFieldNullable](#isfieldnullable)|Возвращает ненулевое значение, если указанное поле в текущей записи может быть присвоено значение null (значение не имеющая).|
|[CRecordset::IsOpen](#isopen)|Возвращает ненулевое значение, если `Open` уже был вызван ранее.|
|[CRecordset::Move](#move)|Устанавливает набор записей на указанное количество записей из текущей записи в любом направлении.|
|[CRecordset::MoveFirst](#movefirst)|Помещает текущей записи на первой записи в наборе записей. Для проверки `IsBOF` первого.|
|[CRecordset::MoveLast](#movelast)|Помещает текущей записи на последней записи или на последний набор строк. Для проверки `IsEOF` первого.|
|[CRecordset::MoveNext](#movenext)|На следующей записи или следующего набора строк, помещает текущей записи. Для проверки `IsEOF` первого.|
|[CRecordset::MovePrev](#moveprev)|Помещает текущей записи в предыдущей записи или в предыдущем наборе строк. Для проверки `IsBOF` первого.|
|[CRecordset::OnSetOptions](#onsetoptions)|Вызывается, чтобы задать параметры (используется для выбора) для указанной инструкции ODBC.|
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|Вызывается для задания параметров (используется в центре обновления) для указанной инструкции ODBC.|
|[CRecordset::Open](#open)|Получение таблицы или выполнять запрос, который представляет набор записей, открывает набор записей.|
|[CRecordset::RefreshRowset](#refreshrowset)|Обновляет данные и состояние указанные строки.|
|[Метод CRecordset::Requery](#requery)|Выполняет запрос набора записей, еще раз, чтобы обновить выбранные записи.|
|[CRecordset::SetAbsolutePosition](#setabsoluteposition)|Устанавливает набор записей на запись, соответствующая указанный номер.|
|[CRecordset::SetBookmark](#setbookmark)|Устанавливает набор записей на записи, указанные на закладки.|
|[CRecordset::SetFieldDirty](#setfielddirty)|Помечает указанного поля в текущей записи, как измененный.|
|[CRecordset::SetFieldNull](#setfieldnull)|Задает значение указанного поля в текущей записи значение null (значение не имеющая).|
|[CRecordset::SetLockingMode](#setlockingmode)|Задает режим блокировки «оптимистичный» блокировка (по умолчанию) или «пессимистической» блокировки. Определяет, как блокировки записей для обновления.|
|[CRecordset::SetParamNull](#setparamnull)|Присваивает указанному параметру значение null (значение не имеющая).|
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|Помещает курсор на указанную строку в наборе строк.|
|[CRecordset::SetRowsetSize](#setrowsetsize)|Указывает количество записей, которые вы хотите получить во время выборки.|
|[CRecordset::Update](#update)|Завершает `AddNew` или `Edit` операции путем сохранения новых или измененных данных в источнике данных.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CRecordset::m_hstmt](#m_hstmt)|Содержит дескриптор инструкции ODBC для набора записей. Введите `HSTMT`.|
|[CRecordset::m_nFields](#m_nfields)|Содержит номер поля элементов данных в наборе записей. Введите `UINT`.|
|[CRecordset::m_nParams](#m_nparams)|Содержит количество элементов данных параметров в наборе записей. Введите `UINT`.|
|[CRecordset::m_pDatabase](#m_pdatabase)|Содержит указатель на `CDatabase` объекта, через который набор записей подключен к источнику данных.|
|[CRecordset::m_strFilter](#m_strfilter)|Содержит `CString` , указывающий язык структурированных запросов (SQL) `WHERE` предложение. Используемый в качестве фильтра для выбора только те записи, которые соответствуют определенным критериям.|
|[CRecordset::m_strSort](#m_strsort)|Содержит `CString` , указывающий SQL `ORDER BY` предложение. Позволяет указать способ сортировки записей.|

## <a name="remarks"></a>Примечания

Известный как «набора записей» `CRecordset` объекты обычно используются в двух формах: динамических подмножеств данных и моментальных снимков. Подмножества остается синхронизированным с обновлениями данных, сделанные другими пользователями. Моментальный снимок — статическое представление данных. Каждая форма представляет набор записей, составляет при открытии набора записей, но во время перехода к записи в подмножества, она отражает изменения, внесенные в запись впоследствии других пользователей или других наборов записей в приложении.

> [!NOTE]
>  Если вы работаете с классами объектов доступа к данным (DAO) вместо классов Open Database Connectivity (ODBC), используйте класс [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) вместо этого. Дополнительные сведения см. в статье [Обзор: программирования баз данных,](../../data/data-access-programming-mfc-atl.md).

Чтобы работать с любого вида записей, обычно производного класса набор записей для конкретного приложения из `CRecordset`. Наборы записей выбора записей из источника данных, а затем вы сможете:

- Просмотрите записи.

- Обновите записи и укажите режим блокировки.

- Фильтровать набор записей, чтобы ограничить записи, которые он выбирает из доступных в источнике данных.

- Сортировка набора записей.

- Параметризация набора записей для настройки его выбора с информацией, не известных до времени выполнения.

Чтобы использовать класс, откройте базу данных и создайте объект набора записей, передав конструктору указатель на вашей `CDatabase` объекта. Затем вызовите набора записей `Open` функция-член, где можно указать, является ли объект подмножества или моментального снимка. Вызов `Open` выбирает данные из источника данных. После открытия объекта набора записей, используйте его члена функции и данным-членам прокручивать записи и выполняют с ними. Доступные операции зависят от, является ли объект подмножества или моментального снимка, обновляемых или только для чтения (это зависит от возможностей источника данных, Open Database Connectivity (ODBC)), и того, реализуется ли пакетная выборка строк. Для обновления записей, которые могут были изменены или добавлены с момента `Open` вызывать, вызвать для объекта `Requery` функция-член. Вызов объекта `Close` члена функции и уничтожьте объект, после завершения работы с его.

В производном `CRecordset` класса, обмен полями (RFX) записей или блочный обмен полей записей (Bulk RFX) используется для поддержки операций чтения и обновления полей записей.

Дополнительные сведения о обмен полями наборов записей и записи, см. в статьях [Обзор: программирования баз данных,](../../data/data-access-programming-mfc-atl.md), [записей (ODBC)](../../data/odbc/recordset-odbc.md), [набор записей: получение записей (ODBC) ](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md), и [обмен полями (RFX) записей](../../data/odbc/record-field-exchange-rfx.md). Фокус на подмножества и моментальные снимки, см. в статьях [динамический набор](../../data/odbc/dynaset.md) и [моментального снимка](../../data/odbc/snapshot.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CRecordset`

## <a name="requirements"></a>Требования

**Заголовок:** afxdb.h

##  <a name="addnew"></a>  CRecordset::AddNew

Подготавливает для добавления новой записи в таблицу.

```
virtual void AddNew();
```

### <a name="remarks"></a>Примечания

Необходимо вызвать [Requery](#requery) функцию-член для вновь добавленной записи см. в разделе. Поля записи, первоначально равно Null. (В терминологии связанных баз данных, значение Null означает, что «предложений having нет значения» и не совпадает со значением NULL в C++). Чтобы завершить операцию, необходимо вызвать [обновления](#update) функция-член. `Update` Сохраняет изменения в источнике данных.

> [!NOTE]
>  Если вы реализовали выборка строк, нельзя вызывать `AddNew`. Это приведет к утверждение, вызвавшее сбой. Несмотря на то что класс `CRecordset` не предоставляет механизм для обновления пакетов строк данных, можно создавать собственные функции с помощью функции ODBC API `SQLSetPos`. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`AddNew` Подготавливает новую, пустую запись, с помощью поля элементов данных набора записей. После вызова метода `AddNew`, задайте нужные значения в поля элементов данных набора записей. (Нет необходимости вызывать [изменить](#edit) функция-член для этой цели; используйте `Edit` только для существующих записей.) При последующем вызове `Update`, измененные значения в поля элементов данных сохраняются в источнике данных.

> [!CAUTION]
>  Если вы прокрутите до новой записи перед вызовом метода `Update`, новой записи теряется, и предоставляется без предупреждения.

Если источник данных поддерживает транзакции, можно сделать ваши `AddNew` вызовов, часть транзакции. Дополнительные сведения о транзакциях см. в разделе класса [CDatabase](../../mfc/reference/cdatabase-class.md). Обратите внимание, что следует вызывать [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) перед вызовом `AddNew`.

> [!NOTE]
>  Для динамических подмножеств данных новые записи добавляются в набор записей как последнюю запись. Добавленных записей не добавляются к моментальным снимкам; необходимо вызвать метод `Requery` для обновления набора записей.

Недопустимо вызывать `AddNew` для объекта recordset, `Open` функция-член не был вызван. Объект `CDBException` возникает исключение при вызове метода `AddNew` для объекта recordset, который не может быть добавлен к. Можно определить ли набор записей является обновляемым, вызвав [CanAppend](#canappend).

Дополнительные сведения см. в следующих статьях: [набор записей: принцип наборы записей обновления записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [набор записей: Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), и [транзакции () ODBC)](../../data/odbc/transaction-odbc.md).

### <a name="example"></a>Пример

См. в статье [транзакции: выполнение транзакции в наборе записей (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

##  <a name="canappend"></a>  CRecordset::CanAppend

Определяет, допускает ли ранее открывавшихся набора записей для добавления новых записей.

```
BOOL CanAppend() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей разрешает добавление новых записей; в противном случае 0. `CanAppend` Возвращает 0, если вы открыли набора записей только для чтения.

##  <a name="canbookmark"></a>  CRecordset::CanBookmark

Определяет, допускает ли набор записей для помечают их с помощью закладок.

```
BOOL CanBookmark() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей поддерживает закладки; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция не зависит от `CRecordset::useBookmarks` в диалоговом окне *dwOptions* параметр [откройте](#open) функция-член. `CanBookmark` Указывает ли конкретного драйвера ODBC и курсор типа поддержки закладки. `CRecordset::useBookmarks` Указывает, будет ли доступна, закладки, если они поддерживаются.

> [!NOTE]
>  Закладки не поддерживаются в последовательным.

Дополнительные сведения о закладок и навигации набор записей, см. в статьях [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="cancel"></a>  CRecordset::Cancel

Запросы, что источник данных отмена выполняемой асинхронной операции или процесс из второго потока.

```
void Cancel();
```

### <a name="remarks"></a>Примечания

Обратите внимание, что классам ODBC библиотеки MFC больше не использовать асинхронной обработки; для выполнения асинхронной операции, необходимо непосредственно вызвать функцию ODBC API `SQLSetConnectOption`. Дополнительные сведения см. в разделе «Выполнение функции асинхронно» *руководство по программированию ODBC SDK*.

##  <a name="cancelupdate"></a>  CRecordset::CancelUpdate

Отменяет все ожидающие обновления, из-за [изменить](#edit) или [AddNew](#addnew) операции, прежде чем [обновления](#update) вызывается.

```
void CancelUpdate();
```

### <a name="remarks"></a>Примечания

> [!NOTE]
>  Эта функция-член не применим наборы записей, в которых используется выборка строк, так как такие наборы записей не может вызвать `Edit`, `AddNew`, или `Update`. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Если включена проверка автоматического поля "грязные", `CancelUpdate` восстановите переменные-члены в значения, они имели до `Edit` или `AddNew` был вызван; в противном случае — значение, останется изменения значений. По умолчанию автоматическое поля включена проверка при открытии набора записей. Чтобы отключить его, необходимо указать `CRecordset::noDirtyFieldCheck` в *dwOptions* параметр [откройте](#open) функция-член.

Дополнительные сведения об обновлении данных см. в статье [набор записей: Добавление, обновление и удаление записей (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).

##  <a name="canrestart"></a>  CRecordset::CanRestart

Определяет, допускает ли набор записей перезапуск его запроса (чтобы обновить свои записи), вызвав `Requery` функция-член.

```
BOOL CanRestart() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если обновление разрешено; в противном случае 0.

##  <a name="canscroll"></a>  CRecordset::CanScroll

Определяет, допускает ли прокрутка набора записей.

```
BOOL CanScroll() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей позволяет прокрутку; в противном случае 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения о прокрутке см. в статье [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="cantransact"></a>  CRecordset::CanTransact

Определяет, допускает ли набор записей транзакций.

```
BOOL CanTransact() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей позволяет транзакции; в противном случае 0.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в статье [транзакции (ODBC)](../../data/odbc/transaction-odbc.md).

##  <a name="canupdate"></a>  CRecordset::CanUpdate

Определяет, возможно ли обновление набора записей.

```
BOOL CanUpdate() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если можно обновить набор записей; в противном случае 0.

### <a name="remarks"></a>Примечания

Набор записей могут быть доступны только для чтения, если базовый источник данных доступен только для чтения, или если вы указали `CRecordset::readOnly` в *dwOptions* параметра при открытии набора записей.

##  <a name="checkrowseterror"></a>  CRecordset::CheckRowsetError

Вызывается для обработки ошибок, возникающих при выполнении записи выборки.

```
virtual void CheckRowsetError(RETCODE nRetCode);
```

### <a name="parameters"></a>Параметры

*nRetCode*<br/>
Код возврата функции ODBC API. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

Это виртуальная функция-член обрабатывает ошибки, возникающие при записи и полезно использовать во время массовой выборке строк. Вы можете рассмотреть возможность переопределения `CheckRowsetError` для реализации обработки ошибок.

`CheckRowsetError` вызывается автоматически при выполнении операции навигации курсора, таких как `Open`, `Requery`, или любой `Move` операции. Он передается возвращаемое значение функции ODBC API `SQLExtendedFetch`. В следующей таблице перечислены возможные значения для *nRetCode* параметра.

|nRetCode|Описание|
|--------------|-----------------|
|ЗНАЧЕНИЕ SQL_SUCCESS, УКАЗЫВАЯ|Функция успешно завершена; Дополнительные сведения недоступны.|
|SQL_SUCCESS_WITH_INFO|Функция успешно завершена, возможно с некритичные ошибки. Дополнительные сведения можно получить путем вызова `SQLError`.|
|SQL_NO_DATA_FOUND|Выбраны все строки из результирующего набора.|
|ЗНАЧЕНИЕ SQL_ERROR|Сбой функции. Дополнительные сведения можно получить путем вызова `SQLError`.|
|SQL_INVALID_HANDLE|Сбой функции из-за недопустимый дескриптор дескриптора соединения и дескриптора инструкции. Это указывает на программную ошибку. Дополнительные сведения недоступны из `SQLError`.|
|SQL_STILL_EXECUTING|Функция, которая запущена в асинхронном режиме по-прежнему выполняется. Обратите внимание, что по умолчанию MFC никогда не будет передавать это значение `CheckRowsetError`; MFC продолжит вызова `SQLExtendedFetch` пока она больше не возвращает значение SQL_STILL_EXECUTING.|

Дополнительные сведения о `SQLError`, см. в Windows SDK. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="close"></a>  CRecordset::Close

Закрывает набор записей.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

Освобождении ODBC HSTMT и всю память framework, выделенных для набора записей. Обычно после вызова метода `Close`, удалить объект recordset C++, если он был выделен с помощью **новый**.

Можно вызвать `Open` снова после вызова метода `Close`. Это позволяет повторно использовать объект recordset. Альтернативой является вызов `Requery`.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#17](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]

##  <a name="crecordset"></a>  CRecordset::CRecordset

Создает объект `CRecordset`.

```
CRecordset(CDatabase* pDatabase = NULL);
```

### <a name="parameters"></a>Параметры

*pDatabase*<br/>
Содержит указатель на `CDatabase` объект или значение NULL. Если значение не NULL и `CDatabase` объекта `Open` функция-член не был вызван для его подключения к источнику данных, пытается открыть его автоматически во время свой собственный набор записей `Open` вызова. Если передать значение NULL, `CDatabase` объект создается и подключение с использованием источника данных, вы указали при производного класса набора записей с помощью классов.

### <a name="remarks"></a>Примечания

Вы можете использовать `CRecordset` напрямую или являются производными класс конкретного приложения из `CRecordset`. ClassWizard можно использовать для формирования классов набора записей.

> [!NOTE]
>  Производный класс *необходимо* предоставить собственный конструктор. В конструкторе производного класса, вызовите конструктор `CRecordset::CRecordset`, передавая ему соответствующие параметры вместе.

Передать NULL в конструктор набора записей для `CDatabase` объект создан и подключен для вас автоматически. Это полезно сокращенное свойство, которое не требуется для создания и подключения `CDatabase` объекта до создания набора записей.

### <a name="example"></a>Пример

Дополнительные сведения см. в статье [набор записей: объявление класса для таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

##  <a name="delete"></a>  CRecordset::Delete

Удаляет текущую запись.

```
virtual void Delete();
```

### <a name="remarks"></a>Примечания

После успешного удаления, элементам данных полей присваивается значение Null, и необходимо явно вызвать один из `Move` функции, чтобы отказаться от использования удаленной записи. Когда необходимо перемещение удаленной записи, не поддерживается вернуться к нему. Если источник данных поддерживает транзакции, можно сделать `Delete` вызовов, часть транзакции. Дополнительные сведения см. в статье [транзакции (ODBC)](../../data/odbc/transaction-odbc.md).

> [!NOTE]
>  Если вы реализовали выборка строк, нельзя вызывать `Delete`. Это приведет к утверждение, вызвавшее сбой. Несмотря на то что класс `CRecordset` не предоставляет механизм для обновления пакетов строк данных, можно создавать собственные функции с помощью функции ODBC API `SQLSetPos`. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

> [!CAUTION]
>  Набор записей должно быть обновляемым и должен существовать допустимой записи текущего набора записей при вызове `Delete`; в противном случае возникает ошибка. Например, если удалить запись, но не прокручиваются при перемещении к новой записи перед вызовом метода `Delete` , `Delete` вызывает [CDBException](../../mfc/reference/cdbexception-class.md).

В отличие от [AddNew](#addnew) и [изменить](#edit), вызов `Delete` должен следовать вызов [обновления](#update). Если `Delete` вызов завершается ошибкой, данные поля, элементы остаются без изменений.

### <a name="example"></a>Пример

Этот пример набора записей, созданные в кадре функции. В примере предполагается существование `m_dbCust`, переменную-член типа `CDatabase` уже подключен к источнику данных.

[!code-cpp[NVC_MFCDatabase#18](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]

##  <a name="dobulkfieldexchange"></a>  CRecordset::DoBulkFieldExchange

Вызывается для обмена массового строк данных из источника данных в набор записей. Реализует блочный обмен полей записей (Bulk RFX).

```
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Параметры

*PFX-файл*<br/>
Указатель на [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) объекта. Платформа будет уже настроили этот объект для указать контекст операции обмена поля.

### <a name="remarks"></a>Примечания

При реализации выборка строк, платформа вызывает эту функцию-член автоматически передавать данные из источника данных объекта набора записей. `DoBulkFieldExchange` также привязывает элементы данных параметра, если таковое имеется, соответствует заполнителям параметров в строке инструкции SQL для выбора набора записей.

Если выборка строк не реализована, платформа вызывает [DoFieldExchange](#dofieldexchange). Чтобы реализовать выборка строк, необходимо указать `CRecordset::useMultiRowFetch` параметр *dwOptions* параметр в [откройте](#open) функция-член.

> [!NOTE]
> `DoBulkFieldExchange` доступен только в том случае, если вы используете класс, производный от `CRecordset`. Если вы создали объект набора записей непосредственно из `CRecordset`, необходимо вызвать [GetFieldValue](#getfieldvalue) функция-член для извлечения данных.

Блочный обмен полей записей (Bulk RFX) аналогичен обмен полями записей (RFX). Данные автоматически передаются из источника данных в объект набора записей. Тем не менее, нельзя вызывать `AddNew`, `Edit`, `Delete`, или `Update` для передачи изменений в источнике данных. Класс `CRecordset` в настоящее время не предоставляет механизм для обновления пакетов строк данных; тем не менее, можно создавать собственные функции с помощью функции ODBC API `SQLSetPos`.

Обратите внимание, что ClassWizard не поддерживает блочный обмен полей записей; Таким образом, необходимо переопределить `DoBulkFieldExchange` вручную, вызовы функций Bulk RFX. Дополнительные сведения об этих функциях см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md).

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Дополнительные сведения см. в статье [обмен полей записей (RFX)](../../data/odbc/record-field-exchange-rfx.md).

##  <a name="dofieldexchange"></a>  CRecordset::DoFieldExchange

Вызывается для обмена данными (в обоих направлениях) между элементами данных полей набора записей и соответствующая запись в источнике данных. Обмен полями (RFX) записей реализует.

```
virtual void DoFieldExchange(CFieldExchange* pFX);
```

### <a name="parameters"></a>Параметры

*PFX-файл*<br/>
Указатель на [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) объекта. Платформа будет уже настроили этот объект для указать контекст операции обмена поля.

### <a name="remarks"></a>Примечания

Выборка строк не реализован, платформа вызывает эту функцию-член для автоматически обмена данными между элементами данных полей объекта набора записей и соответствующих столбцов текущей записи в источнике данных. `DoFieldExchange` также привязывает элементы данных параметра, если таковое имеется, соответствует заполнителям параметров в строке инструкции SQL для выбора набора записей.

Если реализован выборка строк, платформа вызывает [DoBulkFieldExchange](#dobulkfieldexchange). Чтобы реализовать выборка строк, необходимо указать `CRecordset::useMultiRowFetch` параметр *dwOptions* параметр в [откройте](#open) функция-член.

> [!NOTE]
> `DoFieldExchange` доступен только в том случае, если вы используете класс, производный от `CRecordset`. Если вы создали объект набора записей непосредственно из `CRecordset`, необходимо вызвать [GetFieldValue](#getfieldvalue) функция-член для извлечения данных.

Exchange поля данных, называемый обмен полями записей (RFX), работает в обоих направлениях: от объекта набора элементов данных полей сопоставляются с полями записей в источнике данных, а также из записи в источнике данных в объект набора записей.

Единственным действием, обычно необходимо выполнить для реализации `DoFieldExchange` для набора записей производный класс является создание класса с помощью классов и укажите имена и типы данных элементов данных полей. Можно также добавить код, что ClassWizard записывает указать параметризованные члены данных или иметь дело с все столбцы, которые динамической привязкой. Дополнительные сведения см. в статье [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).

При объявлении класса производный набор записей с помощью классов, мастер создает переопределение `DoFieldExchange` , который похож на приведенный ниже:

[!code-cpp[NVC_MFCDatabase#19](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]

Дополнительные сведения о функции RFX см. в разделе [функции обмена полями записей](../../mfc/reference/record-field-exchange-functions.md).

Дополнительные примеры и сведения об `DoFieldExchange`, см. в статье [обмен полями записей: принцип работы RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Общие сведения о RFX см. в статье [обмен полями записи](../../data/odbc/record-field-exchange-rfx.md).

##  <a name="edit"></a>  CRecordset::Edit

Позволяет вносить изменения текущей записи.

```
virtual void Edit();
```

### <a name="remarks"></a>Примечания

После вызова метода `Edit`, элементами данных полей можно изменить напрямую, сбросив их значения. Операция завершена, при последующем вызове [обновления](#update) функция-член для сохранения изменений в источнике данных.

> [!NOTE]
>  Если вы реализовали выборка строк, нельзя вызывать `Edit`. Это приведет к утверждение, вызвавшее сбой. Несмотря на то что класс `CRecordset` не предоставляет механизм для обновления пакетов строк данных, можно создавать собственные функции с помощью функции ODBC API `SQLSetPos`. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`Edit` сохраняет значения членов данных набора записей. При вызове метода `Edit`, внесите изменения, затем вызвать `Edit` опять же, восстанавливаются значения записи он находился перед первым `Edit` вызова.

В некоторых случаях может потребоваться обновить столбец, делая Null (содержащий нет данных). Чтобы сделать это, вызовите [метод SetFieldNull](#setfieldnull) со значением параметра равным ИСТИНА – чтобы пометить поле значение Null; это также приводит к обновляемого столбца. Если необходимо добавить поле для записи к источнику данных, несмотря на то, что его значение не изменилось, вызовите [SetFieldDirty](#setfielddirty) со значением параметра равным TRUE. Это работает, даже если оно имело значение Null.

Если источник данных поддерживает транзакции, можно сделать `Edit` вызовов, часть транзакции. Обратите внимание, что следует вызывать [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) перед вызовом `Edit` и после открытия набора записей. Также Обратите внимание, что при вызове [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) он не может заменить за вызов метода `Update` для завершения `Edit` операции. Дополнительные сведения о транзакциях см. в разделе класса [CDatabase](../../mfc/reference/cdatabase-class.md).

В зависимости от текущего режима блокировки, обновляемой записи может быть заблокирован `Edit` до вызова метода `Update` или прокрутки на другую запись или он может быть заблокирован только во время `Edit` вызова. Можно изменить режим блокировки с [SetLockingMode](#setlockingmode).

Предыдущее значение текущей записи восстанавливается в том случае, если прокрутить записи до вызова метода `Update`. Объект `CDBException` возникает исключение при вызове метода `Edit` для набора записей, которое не может быть обновлено или отсутствует текущая запись.

Дополнительные сведения см. в статьях [транзакции (ODBC)](../../data/odbc/transaction-odbc.md) и [набор записей: Блокировка записей (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#20](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]

##  <a name="flushresultset"></a>  CRecordset::FlushResultSet

Возвращает следующий результирующий набор предопределенного запроса (хранимой процедуры), при наличии нескольких результирующих наборов.

```
BOOL FlushResultSet();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если имеются дополнительные результирующие наборы, требуется получить; в противном случае 0.

### <a name="remarks"></a>Примечания

Следует вызывать `FlushResultSet` только при использовании завершит обработку на текущий результирующий набор курсора. Обратите внимание, что при извлечении следующему результирующему набору, вызвав `FlushResultSet`, курсор не допускается для этого результирующего набора; следует вызывать [MoveNext](#movenext) после вызова функции-члена `FlushResultSet`.

Если предопределенного запроса использует выходной параметр или входных и выходных параметров, необходимо вызвать `FlushResultSet` пока не будет возвращено `FALSE` (значение 0), чтобы получить эти значения параметров.

`FlushResultSet` вызывает функцию ODBC API `SQLMoreResults`. Если `SQLMoreResults` возвращает значение SQL_ERROR или SQL_INVALID_HANDLE, затем `FlushResultSet` приведет к возникновению исключения. Дополнительные сведения о `SQLMoreResults`, см. в Windows SDK.

Хранимой процедуре необходимо привязаны поля, если вы хотите вызвать `FlushResultSet`.

### <a name="example"></a>Пример

В следующем коде предполагается, что `COutParamRecordset` — `CRecordset`-производного объекта, на основании предопределенного запроса с входным и выходным параметром и наличие нескольких результирующих наборов. Обратите внимание, структура [DoFieldExchange](#dofieldexchange) переопределить.

[!code-cpp[NVC_MFCDatabase#21](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]

[!code-cpp[NVC_MFCDatabase#22](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]

##  <a name="getbookmark"></a>  CRecordset::GetBookmark

Получает значение текущей записи.

```
void GetBookmark(CDBVariant& varBookmark);
```

### <a name="parameters"></a>Параметры

*varBookmark*<br/>
Ссылку на [CDBVariant](../../mfc/reference/cdbvariant-class.md) объект, представляющий закладку на текущей записи.

### <a name="remarks"></a>Примечания

Чтобы определить, поддерживаются ли закладки для объекта recordset, вызовите [CanBookmark](#canbookmark). Чтобы сделать закладки доступным, если они поддерживаются, необходимо задать `CRecordset::useBookmarks` в диалоговом окне *dwOptions* параметр [откройте](#open) функция-член.

> [!NOTE]
>  Если закладки-это неподдерживаемый или недоступен, вызов метода `GetBookmark` приведет к возникновению исключения. Закладки не поддерживаются в последовательным.

`GetBookmark` присваивает значение закладки для текущей записи к `CDBVariant` объекта. Чтобы вернуться к этой записи в любое время после перехода на другую запись, вызовите [SetBookmark](#setbookmark) с соответствующим `CDBVariant` объекта.

> [!NOTE]
>  После определенных операций записей закладки больше не могут быть допустимы. Например, если вы вызываете `GetBookmark` следуют `Requery`, вы не сможете вернуться к записи с `SetBookmark`. Вызовите [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) для проверки, можно ли безопасно вызов `SetBookmark`.

Дополнительные сведения о закладок и навигации набор записей, см. в статьях [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="getdefaultconnect"></a>  CRecordset::GetDefaultConnect

Вызывается для получения строки подключения по умолчанию.

```
virtual CString GetDefaultConnect();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , содержащий строку подключения по умолчанию.

### <a name="remarks"></a>Примечания

Чтобы получить строку подключения по умолчанию для источника данных, на котором основан набор записей эта функция-член вызывается платформой. ClassWizard реализует эту функцию можно, указав тот же источник данных, используемых в ClassWizard для получения сведений о таблицах и столбцах. Вам будет, вероятно, удобнее полагаться на это подключение по умолчанию при разработке приложения. Но подключения по умолчанию может не подойти для пользователей приложения. Если это так, следует воссоздать эту функцию, удаляя ClassWizard в версии. Дополнительные сведения о строках подключения см. в статье [источника данных (ODBC)](../../data/odbc/data-source-odbc.md).

##  <a name="getdefaultsql"></a>  CRecordset::GetDefaultSQL

Вызывается, чтобы получить строку SQL по умолчанию для выполнения.

```
virtual CString GetDefaultSQL();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , содержащий инструкцию SQL по умолчанию.

### <a name="remarks"></a>Примечания

Для получения оператора SQL по умолчанию, на котором основан набор записей эта функция-член вызывается платформой. Это может быть имя таблицы или SQL **ВЫБЕРИТЕ** инструкции.

Косвенно определите инструкцию SQL по умолчанию путем объявления класса набора записей с ClassWizard и ClassWizard выполняет эту задачу автоматически.

Если вам требуется строка инструкции SQL для собственного использования, вызовите `GetSQL`, который возвращает инструкцию SQL, используемую для выбора записей набора записей в том случае, когда он был открыт. Можно изменить строку SQL по умолчанию в ваш класс переопределение `GetDefaultSQL`. Например, можно указать вызов предопределенного запроса с помощью **ВЫЗОВИТЕ** инструкции. (Обратите внимание, однако, если изменить `GetDefaultSQL`, необходимо также изменить `m_nFields` соответствует количеству столбцов в источнике данных.)

Дополнительные сведения см. в статье [набор записей: объявление класса для таблицы (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).

> [!CAUTION]
>  Имя таблицы будет пустым, если платформа не удалось определить имя таблицы, если указано несколько имен таблиц или **ВЫЗОВИТЕ** инструкция не может быть интерпретирован. Обратите внимание, что при использовании **вызвать** инструкции, не нужно вставить пробел между фигурными скобками и **вызвать** ключевое слово, и не должен вставлять пробелы до фигурная скобка, или перед  **ВЫБЕРИТЕ** ключевое слово в **ВЫБЕРИТЕ** инструкции.

##  <a name="getfieldvalue"></a>  CRecordset::GetFieldValue

Извлекает данные полей в текущей записи.

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
Имя поля.

*varValu*ссылку e A [CDBVariant](../../mfc/reference/cdbvariant-class.md) объект, который будет хранить значение поля.

*nFieldType*<br/>
Тип данных ODBC C поля. Используя значение по умолчанию, DEFAULT_FIELD_TYPE, принудительно `GetFieldValue` определить тип данных C из типа данных SQL, на основе следующей таблице. В противном случае можно указать данные непосредственно введите или выберите совместимый тип данных; Например можно хранить любой тип данных в SQL_C_CHAR.

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

Дополнительные сведения о типах данных ODBC см. в разделах «Типы данных SQL» и «Типы данных C» в приложении D пакета SDK для Windows.

*nIndex*<br/>
Отсчитываемый от нуля индекс поля.

*strValue*<br/>
Ссылку на [CString](../../atl-mfc-shared/reference/cstringt-class.md) объект, который будет хранить значение поля преобразуется в текст, независимо от типа данных поля.

### <a name="remarks"></a>Примечания

Поле можно искать по имени или по индексу. Значение поля можно хранить в любом `CDBVariant` объекта или `CString` объекта.

Если вы реализовали выборка строк, текущей записи всегда находится на первой записи в наборе строк. Чтобы использовать `GetFieldValue` на запись в заданном наборе строк, необходимо сначала вызвать [SetRowsetCursorPosition](#setrowsetcursorposition) функция-член для перемещения курсора на нужные строки в этом наборе строк. Затем вызовите `GetFieldValue` для этой строки. Чтобы реализовать выборка строк, необходимо указать `CRecordset::useMultiRowFetch` параметр *dwOptions* параметр в [откройте](#open) функция-член.

Можно использовать `GetFieldValue` динамически получить поля во время выполнения, а не статически привязка их во время разработки. Например, если вы объявили непосредственно из объекта набора записей `CRecordset`, необходимо использовать `GetFieldValue` для извлечения полей данных; обмен полями записей (RFX) или блочный обмен полей записей (Bulk RFX), не реализованы.

> [!NOTE]
>  При объявлении объекта набора записей не на основе `CRecordset`, не имеют загрузить библиотеку курсоров ODBC. Библиотека курсоров требует, чтобы набор записей по крайней мере один привязанного столбца; Тем не менее, при использовании `CRecordset` напрямую, ни один из столбцов привязаны. Функции-члены [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) и [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) управления, будет ли загружать библиотеку курсоров.

`GetFieldValue` вызывает функцию ODBC API `SQLGetData`. Если драйвер выводит значение SQL_NO_TOTAL фактическую длину значение поля, `GetFieldValue` возникло исключение. Дополнительные сведения о `SQLGetData`, см. в Windows SDK.

### <a name="example"></a>Пример

В следующем примере кода показаны вызовы `GetFieldValue` для объекта recordset, объявленные непосредственно из `CRecordset`.

[!code-cpp[NVC_MFCDatabase#23](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]

> [!NOTE]
>  В отличие от классов DAO `CDaoRecordset`, `CRecordset` имеет `SetFieldValue` функция-член. Если вы создаете объект непосредственно из `CRecordset`, он эффективно только для чтения.

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="getodbcfieldcount"></a>  CRecordset::GetODBCFieldCount

Возвращает общее число полей объекта набора записей.

```
short GetODBCFieldCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число полей в наборе записей.

### <a name="remarks"></a>Примечания

Дополнительные сведения о создании наборов записей, см. в статье [набор записей: Создание и закрытие наборов записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

##  <a name="getodbcfieldinfo"></a>  CRecordset::GetODBCFieldInfo

Получает сведения о полях в набор записей.

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
Имя поля.

*FieldInfo*<br/>
Ссылку на `CODBCFieldInfo` структуры.

*nIndex*<br/>
Отсчитываемый от нуля индекс поля.

### <a name="remarks"></a>Примечания

Одну версию функции позволяет искать поле по имени. Другая версия позволяет искать поле по индексу.

Описание сведений, возвращаемых, см. в разделе [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md) структуры.

Дополнительные сведения о создании наборов записей, см. в статье [набор записей: Создание и закрытие наборов записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

##  <a name="getrecordcount"></a>  CRecordset::GetRecordCount

Определяет размер набора записей.

```
long GetRecordCount() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число записей в наборе записей; 0, если набор записей не содержит записей; или -1, если не удается определить число записей.

### <a name="remarks"></a>Примечания

> [!CAUTION]
>  Число записей как «верхнего предела,» запись новейшую, но показано, как пользователь перемещает по записям. Общее количество записей известен только после пользователя была достигнута последняя запись. Для повышения производительности, счетчик не обновляется при вызове `MoveLast`. Чтобы подсчитать число записей самостоятельно, вызовите `MoveNext` пока `IsEOF` возвращает ненулевое значение. Добавление записи с помощью `CRecordset:AddNew` и `Update` увеличивает это число; удаление записи с помощью `CRecordset::Delete` уменьшает значение счетчика.

##  <a name="getrowsetsize"></a>  CRecordset::GetRowsetSize

Получает текущее значение для числа строк, которые вы хотите получить во время операции выборки.

```
DWORD GetRowsetSize() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число строк во время операции выборки.

### <a name="remarks"></a>Примечания

Если вы используете выборка строк, размер набора строк по умолчанию при открытии набора записей — 25. в противном случае равно 1.

Чтобы реализовать выборка строк, необходимо указать `CRecordset::useMultiRowFetch` в диалоговом окне *dwOptions* параметр [откройте](#open) функция-член. Чтобы изменить параметр размера набора строк, вызвать [SetRowsetSize](#setrowsetsize).

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="getrowsfetched"></a>  CRecordset::GetRowsFetched

Определяет, сколько записей фактически были получены после выборки.

```
DWORD GetRowsFetched() const;
```

### <a name="return-value"></a>Возвращаемое значение

Число строк, полученных из источника данных после операции выборки.

### <a name="remarks"></a>Примечания

Это полезно в тех случаях, когда вы реализовали выборка строк. Размер набора строк обычно указывает, сколько строк будет извлекаться из выборки; Тем не менее общее число строк в наборе записей также влияет на количество строк, которые будут извлечены в наборе строк. Например, если набор записей содержит 10 записей по размер набора строк, равным 4, затем обход набора записей путем вызова `MoveNext` приведет к окончательного набора строк, имеющие только 2 записи.

Чтобы реализовать выборка строк, необходимо указать `CRecordset::useMultiRowFetch` в диалоговом окне *dwOptions* параметр [откройте](#open) функция-член. Чтобы указать размер набора строк, вызовите [SetRowsetSize](#setrowsetsize).

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#24](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]

##  <a name="getrowstatus"></a>  CRecordset::GetRowStatus

Получает состояние для строки в текущем наборе строк.

```
WORD GetRowStatus(WORD wRow) const;
```

### <a name="parameters"></a>Параметры

*wRow*<br/>
От единицы позиция строки в текущем наборе строк. Это значение находится в диапазоне от 1 до размера набора строк.

### <a name="return-value"></a>Возвращаемое значение

Значение состояния для строки. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

`GetRowStatus` Возвращает значение, указывающее любое изменение в состоянии, чтобы строка с момента его последнего полученных из источника данных, или нет соответствующей строки для *wRow* была сделана выборка. В следующей таблице перечислены возможные возвращаемые значения.

|Значение состояния|Описание|
|------------------|-----------------|
|SQL_ROW_SUCCESS|Строка не содержит изменений.|
|SQL_ROW_UPDATED|Строка была обновлена.|
|ЗНАЧЕНИЕ SQL_ROW_DELETED|Строка была удалена.|
|SQL_ROW_ADDED|Строка была добавлена.|
|SQL_ROW_ERROR|Строки не удается извлечь, так как произошла ошибка.|
|SQL_ROW_NOROW|Нет строк, соответствующий *wRow*.|

Дополнительные сведения см. в разделе функции ODBC API `SQLExtendedFetch` в пакете Windows SDK.

##  <a name="getstatus"></a>  CRecordset::GetStatus

Определяет индекс текущей записи в набор записей и наблюдалась ли последнюю запись.

```
void GetStatus(CRecordsetStatus& rStatus) const;
```

### <a name="parameters"></a>Параметры

*rStatus*<br/>
Ссылка на объект `CRecordsetStatus`. Дополнительные сведения см. в разделе "Примечания".

### <a name="remarks"></a>Примечания

`CRecordset` пытается отслеживать индекс, но в некоторых случаях это может оказаться невозможным. См. в разделе [GetRecordCount](#getrecordcount) объяснение.

`CRecordsetStatus` Структура имеет следующий вид:

```cpp
struct CRecordsetStatus
{
    long m_lCurrentRecord;
    BOOL m_bRecordCountFinal;
};
```

Два члена `CRecordsetStatus` имеют следующий смысл:

- `m_lCurrentRecord` Содержит отсчитываемый от нуля индекс текущей записи в наборе записей, если он известен. Если индекс не может быть определен, этот элемент содержит AFX_CURRENT_RECORD_UNDEFINED (-2). Если `IsBOF` — TRUE (пустой набор записей или попытка выполнить прокрутку до первой записи), затем `m_lCurrentRecord` присваивается AFX_CURRENT_RECORD_BOF (-1). Если в первой записи, то он присваивается 0, во-вторых записи 1 и так далее.

- `m_bRecordCountFinal` Ненулевое значение, если было определено общее число записей в наборе. Обычно это необходимо сделать, начиная с первого набора записей и вызов `MoveNext` пока `IsEOF` возвращает ненулевое значение. Если этого элемента равно нулю, записи считаются возвращаемые `GetRecordCount`, если не -1, является только «верхнего предела» количество записей.

##  <a name="getsql"></a>  CRecordset::GetSQL

Вызывайте эту функцию члена, чтобы получить инструкцию SQL, который использовался для выбора записей набора записей в том случае, когда он был открыт.

```
const CString& GetSQL() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект **const** ссылка на `CString` , содержащий инструкции SQL.

### <a name="remarks"></a>Примечания

Как правило, это будет SQL **ВЫБЕРИТЕ** инструкции. Строка, возвращаемая `GetSQL` доступен только для чтения.

Строка, возвращаемая `GetSQL` обычно отличается от любой строки, то может передать в набор записей в *lpszSQL* параметр `Open` функция-член. Это обусловлено записей создает полная инструкция SQL, в зависимости от того, что Вы передали `Open`, указанным с помощью классов, что указано в `m_strFilter` и `m_strSort` данные-члены и любые параметры, возможно, указан. Сведения о том, как набор записей создает Эта инструкция SQL, см. в статье [набор записей: принцип наборы записей выберите записей (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

> [!NOTE]
>  Вызовите эту функцию-член только после вызова метода [откройте](#open).

##  <a name="gettablename"></a>  CRecordset::GetTableName

Возвращает имя таблицы SQL, на котором основан запрос набора записей.

```
const CString& GetTableName() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект **const** ссылка на `CString` , содержащую таблицу, имя, если набор записей на основе таблицы, в противном случае — пустая строка.

### <a name="remarks"></a>Примечания

`GetTableName` допустимо, только если набор записей на основе таблицы, не соединения нескольких таблиц или предопределенного запроса (хранимой процедуры). Имя доступно только для чтения.

> [!NOTE]
>  Вызовите эту функцию-член только после вызова метода [откройте](#open).

##  <a name="isbof"></a>  CRecordset::IsBOF

Возвращает ненулевое значение, если набор записей позиционирует перед первой записью. Отсутствует текущая запись.

```
BOOL IsBOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей не содержит записей или прокручен назад до первой записи; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызов этой функции-члена до перехода от записи к записи дополнительные ли вы вышли перед первой записи в наборе записей. Можно также использовать `IsBOF` вместе с `IsEOF` определить набор записей содержит какие-либо записи или является пустым. Сразу после вызова метода `Open`, если набор записей не содержит записей, `IsBOF` возвращает ненулевое значение. При открытии набора записей, имеющий по крайней мере одну запись, первая запись становится текущей записью и `IsBOF` возвращает 0.

Если первая запись становится текущей записью и вызывается `MovePrev`, `IsBOF` впоследствии будет возвращать ненулевое значение. Если `IsBOF` возвращает ненулевое значение, при вызове метода `MovePrev`, возникает ошибка. Если `IsBOF` возвращает ненулевое значение текущей записи не определен, и любое действие, которое требует текущей записи приведет к ошибке.

### <a name="example"></a>Пример

В этом примере используется `IsBOF` и `IsEOF` для определения границ набора записей, так как код выполняет прокрутку по набору записей в обоих направлениях.

[!code-cpp[NVC_MFCDatabase#25](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]

##  <a name="isdeleted"></a>  CRecordset::IsDeleted

Определяет, был ли удален текущей записи.

```
BOOL IsDeleted() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей располагается на удаленную запись; в противном случае 0.

### <a name="remarks"></a>Примечания

Если вы прокрутите страницу к записи и `IsDeleted` возвращает значение TRUE (ненулевое), а затем необходимо перейти к другой записи, перед тем как выполнять другие операции, набор записей.

Результат `IsDeleted` зависит от многих факторов, таких как ваш тип набора записей ли набор записей обновляемым, ли вы указали `CRecordset::skipDeletedRecords` при открытии набора записей, ли своих пакетов драйверов удаленных записей, и существует ли несколько пользователей.

Дополнительные сведения о `CRecordset::skipDeletedRecords` и драйвер упаковки, см. в разделе [откройте](#open) функция-член.

> [!NOTE]
>  Если вы реализовали выборка строк, не следует вызывать `IsDeleted`. Вместо этого необходимо вызвать [GetRowStatus](#getrowstatus) функция-член. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="iseof"></a>  CRecordset::IsEOF

Возвращает ненулевое значение, если набор записей позиционирует после последней записи. Отсутствует текущая запись.

```
BOOL IsEOF() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей не содержит записей или были прокручены за пределы последней записи; в противном случае 0.

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член, при переходе от записи к записи дополнительные ли вы вышли за пределы последней записи в наборе записей. Можно также использовать `IsEOF` для определения содержит только записи, или пустой набор записей. Сразу после вызова метода `Open`, если набор записей не содержит записей, `IsEOF` возвращает ненулевое значение. При открытии набора записей, имеющий по крайней мере одну запись, первая запись становится текущей записью и `IsEOF` возвращает 0.

Если последняя запись становится текущей записью, при вызове `MoveNext`, `IsEOF` впоследствии будет возвращать ненулевое значение. Если `IsEOF` возвращает ненулевое значение, при вызове метода `MoveNext`, возникает ошибка. Если `IsEOF` возвращает ненулевое значение текущей записи не определен, и любое действие, которое требует текущей записи приведет к ошибке.

### <a name="example"></a>Пример

См. в примере [IsBOF](#isbof).

##  <a name="isfielddirty"></a>  CRecordset::IsFieldDirty

Определяет, был ли изменен элемент данных указанного поля с момента [изменить](#edit) или [AddNew](#addnew) был вызван.

```
BOOL IsFieldDirty(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на член поля данных, состояние которого требуется проверить, или значение NULL, чтобы определить потребность в любом из полей "грязных".

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент данных указанное поле было изменено с момента вызова `AddNew` или `Edit`; в противном случае — 0.

### <a name="remarks"></a>Примечания

Данные в все измененными элементами данных полей должны быть переданы записи в источнике данных при обновлении текущей записи путем вызова [обновление](#update) функцию-член `CRecordset` (вслед за вызовом `Edit` или `AddNew`).

> [!NOTE]
>  Эта функция-член не применим на наборы записей, в которых используется выборка строк. Если вы реализовали выборка строк, затем `IsFieldDirty` всегда будет возвращать значение FALSE и приведет к утверждение, вызвавшее сбой. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Вызов `IsFieldDirty` приведет к сбросу эффектов предыдущих вызовов [SetFieldDirty](#setfielddirty) так, как "грязный" состояние поля вычисляется повторно. В `AddNew` случае, если текущее значение поля, отличается от значения null псевдо, поле задано состояние "грязного". В `Edit` случае, если значение поля, отличается от кэшированное значение, а затем поле также имеет состояние "грязного".

`IsFieldDirty` реализуется с помощью [DoFieldExchange](#dofieldexchange).

Дополнительные сведения о "грязный" флаг см. в статье [набор записей: принцип наборы записей выберите записей (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

##  <a name="isfieldnull"></a>  CRecordset::IsFieldNull

Возвращает ненулевое значение, если указанное поле в текущей записи имеет значение Null (не имеет значения).

```
BOOL IsFieldNull(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на член поля данных, состояние которой вы хотите проверить, или значение NULL, чтобы определить, если поля имеют значение Null.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если элемент данных заданного поля помечается как Null. в противном случае 0.

### <a name="remarks"></a>Примечания

Вызывайте эту функцию члена, чтобы определить, помечен ли элемент данных указанного поля в наборе записей как Null. (В терминологии связанных баз данных, значение Null означает, что «предложений having нет значения» и не совпадает со значением NULL в C++). Если элемент данных поле помечается как Null, то он интерпретируется как столбец текущей записи, для которого не имеет смысла.

> [!NOTE]
>  Эта функция-член не применим на наборы записей, в которых используется выборка строк. Если вы реализовали выборка строк, затем `IsFieldNull` всегда будет возвращать значение FALSE и приведет к утверждение, вызвавшее сбой. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

`IsFieldNull` реализуется с помощью [DoFieldExchange](#dofieldexchange).

##  <a name="isfieldnullable"></a>  CRecordset::IsFieldNullable

Возвращает ненулевое значение, если указанное поле в текущей записи может иметь значение Null (значение не имеющая).

```
BOOL IsFieldNullable(void* pv);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Указатель на член поля данных, состояние которого требуется проверить, или значение NULL, чтобы определить, если значения полей можно присвоить значение Null.

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член для определения ли элемент данных указанное поле значение «NULL» (может быть присвоено значение Null; C++ NULL не является таким же, как значение Null, что в терминологии связанных баз данных, означает, что «предложений having без значения»).

> [!NOTE]
>  Если вы реализовали выборка строк, нельзя вызывать `IsFieldNullable`. Вместо этого необходимо вызвать [GetODBCFieldInfo](#getodbcfieldinfo) функция-член для определения, является ли поле может быть присвоено значение Null. Обратите внимание, что всегда может вызвать `GetODBCFieldInfo`, независимо от того, реализуется ли пакетная выборка строк. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Поле, которое не может иметь значение Null должно иметь значение. При попытке такого поля задать значение NULL, при добавлении или обновлении записи источника данных отклоняет Добавление или обновление, и [обновление](#update) приведет к возникновению исключения. Исключение возникает при вызове `Update`, не в том случае, когда вы вызываете [метод SetFieldNull](#setfieldnull).

Использование значения NULL, первый аргумент функции будет применяться только к функции `outputColumn` поля, не `param` поля. Например вызов

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

будет только при задании `outputColumn` поля NULL; `param` поля не будут затронуты.

Для работы на `param` поля, необходимо указать фактический адрес лица, `param` для работы, такие как:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Это означает, что нельзя задать все `param` поля значение NULL, как и с помощью `outputColumn` поля.

`IsFieldNullable` реализуется с помощью [DoFieldExchange](#dofieldexchange).

##  <a name="isopen"></a>  CRecordset::IsOpen

Определяет, если набор записей уже открыто.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение объекте набора записей [откройте](#open) или [Requery](#requery) ранее был вызван функция-член и набор записей не закрыт; иначе — 0.

##  <a name="m_hstmt"></a>  CRecordset::m_hstmt

Содержит дескриптор ODBC инструкции для структуры данных, типа HSTMT, связанного с набором записей.

### <a name="remarks"></a>Примечания

Каждый запрос к источнику данных ODBC, связанный с HSTMT.

> [!CAUTION]
>  Не используйте `m_hstmt` перед [откройте](#open) был вызван.

Обычно не нужно напрямую обращаться к HSTMT, но которые могут потребоваться для прямого выполнения инструкций SQL. `ExecuteSQL` Функция-член класса `CDatabase` предоставляет пример использования `m_hstmt`.

##  <a name="m_nfields"></a>  CRecordset::m_nFields

Содержит номер поля элементов данных в классе набора записей. то есть число столбцов, выбранных в набор записей из источника данных.

### <a name="remarks"></a>Примечания

Конструктор для класса набора записей необходимо инициализировать `m_nFields` с правильным числом. Если групповая выборка строк не реализована, ClassWizard записывает эту инициализацию автоматически при использовании для объявления класса набора записей. Можно также написать его вручную.

Инфраструктура использует это число для управления взаимодействием между элементами данных полей и соответствующих столбцов текущей записи в источнике данных.

> [!CAUTION]
>  Этот номер должен соответствовать количеству «выходные столбцы», зарегистрированный в `DoFieldExchange` или `DoBulkFieldExchange` после вызова [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) с параметром `CFieldExchange::outputColumn`.

Может привязать столбцы динамически, как описано в статье «набор записей: динамически столбцы привязки данных.» Если сделать это, необходимо увеличить число в `m_nFields` в соответствии с вызовов функции RFX и Bulk RFX вашей `DoFieldExchange` или `DoBulkFieldExchange` функция-член для динамически привязанные столбцы.

Дополнительные сведения см. в статьях [набор записей: динамическая привязка столбцов данных (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) и [набор записей: получение записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

См. в статье [обмен полями записей: использование RFX](../../data/odbc/record-field-exchange-using-rfx.md).

##  <a name="m_nparams"></a>  CRecordset::m_nParams

Содержит количество элементов данных параметров в классе набора записей. то есть запросе набора записей передается число параметров.

### <a name="remarks"></a>Примечания

Если набор записей класс элементов данных параметров, необходимо инициализировать конструктор для класса `m_nParams` с правильным числом. Значение `m_nParams` по умолчанию равно 0. При добавлении элементов данных параметров (которые необходимо сделать вручную) необходимо также вручную добавить инициализацию в конструкторе класса в соответствии с числом параметров (который должен быть по крайней мере число '' заполнители в вашей `m_strFilter` или `m_strSort`строка).

Платформа использует это число, когда он выполняет параметризацию запроса набора записей.

> [!CAUTION]
>  Это число должно соответствовать количеству «params», зарегистрированный в `DoFieldExchange` или `DoBulkFieldExchange` после вызова [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) со значением параметра `CFieldExchange::inputParam`, `CFieldExchange::param`, `CFieldExchange::outputParam`, или `CFieldExchange::inoutParam`.

### <a name="example"></a>Пример

  См. в статьях [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) и [обмен полями записей: использование RFX](../../data/odbc/record-field-exchange-using-rfx.md).

##  <a name="m_pdatabase"></a>  CRecordset::m_pDatabase

Содержит указатель на `CDatabase` объекта, через который набор записей подключен к источнику данных.

### <a name="remarks"></a>Примечания

Эта переменная задается двумя способами. Как правило, передать указатель на уже подключенной `CDatabase` объекта при создании объекта набора записей. Если передать значение NULL вместо этого `CRecordset` создает `CDatabase` объекта для вас и подключает его. В любом случае `CRecordset` сохраняет указатель в этой переменной.

Обычно не требуется напрямую использовать указателем, сохраненным в `m_pDatabase`. При написании собственных расширений для `CRecordset`, тем не менее, может потребоваться использовать указатель. Например, может потребоваться указатель Если вызывается собственные `CDBException`s. Или он может понадобиться, если вам нужно сделать что-нибудь, используя те же `CDatabase` объекта, например выполняющиеся транзакции, Настройка времени ожидания, или вызов `ExecuteSQL` функция-член класса `CDatabase` для выполнения инструкций SQL непосредственно.

##  <a name="m_strfilter"></a>  CRecordset::m_strFilter

После создания объекта набора записей, но перед вызовом его `Open` член функции, используйте этот элемент данных для хранения `CString` содержащий SQL **ГДЕ** предложение.

### <a name="remarks"></a>Примечания

Набор записей эта строка используется для ограничения (или фильтр) выбирается во время записи `Open` или `Requery` вызова. Это полезно для выбора подмножества записей, например «из Калифорнии всех менеджеров по продажам» («состояние = ЦС»). Синтаксис ODBC SQL **ГДЕ** предложение

`WHERE search-condition`

Обратите внимание, что отсутствует **ГДЕ** ключевое слово в строке. Среда .NET framework предоставляет его.

Также можно параметризовать строки фильтра, поместив '' заполнителей, объявлении члена данных параметра в классе для каждого местозаполнителя и передача параметров в набор записей во время выполнения. Это позволяет создавать фильтр во время выполнения. Дополнительные сведения см. в статье [набор записей: Параметризация набора записей (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).

Дополнительные сведения о SQL **ГДЕ** предложений, см. в статье [SQL](../../data/odbc/sql.md). Дополнительные сведения о выборе и фильтрации записей см. в статье [набор записей: фильтрация записей (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#30](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]

##  <a name="m_strsort"></a>  CRecordset::m_strSort

После создания объекта набора записей, но перед вызовом его `Open` член функции, используйте этот элемент данных для хранения `CString` содержащий SQL **ORDER BY** предложение.

### <a name="remarks"></a>Примечания

Набор записей использует эту строку можно отсортировать записи во время выбирается `Open` или `Requery` вызова. Эту функцию можно использовать для сортировки набора записей для одного или нескольких столбцов. Синтаксис ODBC SQL **ORDER BY** предложение

`ORDER BY sort-specification [, sort-specification]...`

где спецификацией сортировки — целое число или имя столбца. Можно также указать восходящий или нисходящий порядок (порядок по возрастанию по умолчанию) путем добавления в список столбцов в строке сортировки либо «ASC» или «DESC». Выбранные записи сортируются сначала по первому столбцу в списке, а затем по второй и т. д. Например могут заказать набор записей «Customers» по фамилии, а затем имя. Число столбцов, которые вы можете получить список зависит от источника данных. Дополнительные сведения см. в разделе Windows SDK.

Обратите внимание, что отсутствует **ORDER BY** ключевое слово в строке. Среда .NET framework предоставляет его.

Дополнительные сведения о предложениях SQL см. в статье [SQL](../../data/odbc/sql.md). Дополнительные сведения о сортировке записей см. в статье [набор записей: сортировка записей (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#31](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]

##  <a name="move"></a>  CRecordset::Move

Перемещает указатель текущей записи в наборе записей, либо вперед или назад.

```
virtual void Move(
    long nRows,
    WORD wFetchType = SQL_FETCH_RELATIVE);
```

### <a name="parameters"></a>Параметры

*nRows*<br/>
Число строк для перемещения вперед или назад. Положительные значения Переход вперед, в конец набора записей. Отрицательные значения перемещение назад, к началу.

*wFetchType*<br/>
Определяет набор строк, `Move` получает. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

Если передать значение 0 для *nRows*, `Move` обновляет текущую запись; `Move` закончится любой текущей `AddNew` или `Edit` режиме, восстанавливается значение текущей записи перед `AddNew` или `Edit` был вызван.

> [!NOTE]
>  При перемещении по набору записей, то нельзя пропустить удаленных записей. См. в разделе [CRecordset::IsDeleted](#isdeleted) Дополнительные сведения. При открытии `CRecordset` с `skipDeletedRecords` параметр set, `Move` утверждает, если *nRows* параметр равен 0. Это предотвращает обновление строк другими клиентскими приложениями, используя те же данные. См. в разделе *dwOption* параметр в [откройте](#open) описание `skipDeletedRecords`.

`Move` изменяет положение набора записей по наборы строк. На основе значений для *nRows* и *wFetchType*, `Move` извлекает соответствующий набор строк, а затем делает первую запись в этом наборе строк текущей записи. Если вы не реализовали выборка строк, размер набора строк всегда равно 1. При выборке набора строк, `Move` напрямую вызывает [CheckRowsetError](#checkrowseterror) функции-члена для обработки всех ошибок, полученные в результате fetch.

В зависимости от значения, указываемые `Move` эквивалентен других `CRecordset` функций-членов. В частности, значение *wFetchType* может указывать на функцию-член, более интуитивно понятный и часто предпочтительный метод для перемещения текущей записи.

В следующей таблице перечислены возможные значения для *wFetchType*, набор строк, `Move` будет получена на основе *wFetchType* и *nRows*и любыми другими член функции соответствующий *wFetchType*.

|wFetchType|Извлеченных строк|Эквивалентный член функции|
|----------------|--------------------|--------------------------------|
|SQL_FETCH_RELATIVE (значение по умолчанию)|Начальный набор строк *nRows* строки из первой строки в текущем наборе строк.||
|SQL_FETCH_NEXT|Следующий набор строк; *nRows* учитывается.|[MoveNext](#movenext)|
|SQL_FETCH_PRIOR ФУНКЦИИ|Предыдущий набор строк; *nRows* учитывается.|[MovePrev](#moveprev)|
|SQL_FETCH_FIRST|Первый набор строк в наборе записей; *nRows* учитывается.|[MoveFirst](#movefirst)|
|SQL_FETCH_LAST|Последний полный набор строк в наборе записей; *nRows* учитывается.|[MoveLast](#movelast)|
|SQL_FETCH_ABSOLUTE|Если *nRows* > 0, набор строк, начинающийся *nRows* строк из начала набора записей. Если *nRows* < 0, набор строк, начинающийся *nRows* строк от конца набора записей. Если *nRows* = 0, то возвращается условие начало файла (записи BOF).|[SetAbsolutePosition](#setabsoluteposition)|
|ИНСТРУКЦИЯ SQL_FETCH_BOOKMARK|Набор строк, начиная со строки, значение которого закладки соответствует *nRows*.|[SetBookmark](#setbookmark)|

> [!NOTE]
>  Для последовательного набора записей `Move` допустимо только со значением SQL_FETCH_NEXT для *wFetchType*.

> [!CAUTION]
>  Вызов `Move` создает исключение, если набор записей не имеющей записей. Чтобы определить, имеет ли набор записей какие-либо записи, вызовите [IsBOF](#isbof) и [IsEOF](#iseof).

> [!NOTE]
>  Если были прокручены за начало или конец набора записей (`IsBOF` или `IsEOF` возвращает ненулевое значение), вызов `Move` возможно вызовет функцию `CDBException`. Например если `IsEOF` возвращает ненулевое значение и `IsBOF` не так, затем `MoveNext` приведет к возникновению исключения, но `MovePrev` не будет.

> [!NOTE]
>  При вызове метода `Move` во время текущей записи обновляемого или добавляемого, обновления будут потеряны без предупреждения.

Дополнительные сведения о перемещении по набору записей, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Дополнительные сведения см. в разделе функции ODBC API `SQLExtendedFetch` в пакете Windows SDK.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCDatabase#28](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]

##  <a name="movefirst"></a>  CRecordset::MoveFirst

Делает первую запись в первый набор строк текущей записи.

```
void MoveFirst();
```

### <a name="remarks"></a>Примечания

Независимо от того, ли выборка строк был реализован это всегда будет первой записи в наборе записей.

Нет необходимости вызывать `MoveFirst` сразу после открытия набора записей. В это время первой записи (если таковые имеются) автоматически становится текущей записью.

> [!NOTE]
>  Эта функция-член не является допустимым для последовательного набора записей.

> [!NOTE]
>  При перемещении по набору записей, то нельзя пропустить удаленных записей. См. в разделе [IsDeleted](#isdeleted) функция-член для сведения.

> [!CAUTION]
>  Вызов любого из `Move` функции вызывает исключение, если набор записей не имеющей записей. Чтобы определить, имеет ли набор записей какие-либо записи, вызовите `IsBOF` и `IsEOF`.

> [!NOTE]
>  При вызове любого из `Move` функции во время текущей записи обновляемого или добавляемого, обновления будут потеряны без предупреждения.

Дополнительные сведения о перемещении по набору записей, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  См. в примере [IsBOF](#isbof).

##  <a name="movelast"></a>  CRecordset::MoveLast

Делает первую запись в последний полный набор строк текущей записи.

```
void MoveLast();
```

### <a name="remarks"></a>Примечания

Если вы не реализовали выборка строк, набор записей имеет размер набора строк, 1, поэтому `MoveLast` просто перемещается к последней записи в наборе записей.

> [!NOTE]
>  Эта функция-член не является допустимым для последовательного набора записей.

> [!NOTE]
>  При перемещении по набору записей, то нельзя пропустить удаленных записей. См. в разделе [IsDeleted](#isdeleted) функция-член для сведения.

> [!CAUTION]
>  Вызов любого из `Move` функции вызывает исключение, если набор записей не имеющей записей. Чтобы определить, имеет ли набор записей какие-либо записи, вызовите `IsBOF` и `IsEOF`.

> [!NOTE]
>  При вызове любого из `Move` функции во время текущей записи обновляемого или добавляемого, обновления будут потеряны без предупреждения.

Дополнительные сведения о перемещении по набору записей, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  См. в примере [IsBOF](#isbof).

##  <a name="movenext"></a>  CRecordset::MoveNext

Делает первую запись в следующем наборе строк текущей записи.

```
void MoveNext();
```

### <a name="remarks"></a>Примечания

Если вы не реализовали выборка строк, набор записей имеет размер набора строк, 1, поэтому `MoveNext` просто переходит к следующей записи.

> [!NOTE]
>  При перемещении по набору записей, то нельзя пропустить удаленных записей. См. в разделе [IsDeleted](#isdeleted) функция-член для сведения.

> [!CAUTION]
>  Вызов любого из `Move` функции вызывает исключение, если набор записей не имеющей записей. Чтобы определить, имеет ли набор записей какие-либо записи, вызовите `IsBOF` и `IsEOF`.

> [!NOTE]
>  Кроме того, рекомендуется вызывать `IsEOF` перед вызовом `MoveNext`. Например, если были прокручены за пределами объекта recordset `IsEOF` будет возвращать ненулевое значение; следующий вызов `MoveNext` вызовет исключение.

> [!NOTE]
>  При вызове любого из `Move` функции во время текущей записи обновляемого или добавляемого, обновления будут потеряны без предупреждения.

Дополнительные сведения о перемещении по набору записей, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  См. в примере [IsBOF](#isbof).

##  <a name="moveprev"></a>  CRecordset::MovePrev

Делает первую запись в предыдущем наборе строк текущей записи.

```
void MovePrev();
```

### <a name="remarks"></a>Примечания

Если вы не реализовали выборка строк, набор записей имеет размер набора строк, 1, поэтому `MovePrev` просто перемещается к предыдущей записи.

> [!NOTE]
>  Эта функция-член не является допустимым для последовательного набора записей.

> [!NOTE]
>  При перемещении по набору записей, то нельзя пропустить удаленных записей. См. в разделе [IsDeleted](#isdeleted) функция-член для сведения.

> [!CAUTION]
>  Вызов любого из `Move` функции вызывает исключение, если набор записей не имеющей записей. Чтобы определить, имеет ли набор записей какие-либо записи, вызовите `IsBOF` и `IsEOF`.

> [!NOTE]
>  Кроме того, рекомендуется вызывать `IsBOF` перед вызовом `MovePrev`. Например, если переход выполнен набор записей `IsBOF` будет возвращать ненулевое значение; следующий вызов `MovePrev` вызовет исключение.

> [!NOTE]
>  При вызове любого из `Move` функции во время текущей записи обновляемого или добавляемого, обновления будут потеряны без предупреждения.

Дополнительные сведения о перемещении по набору записей, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

### <a name="example"></a>Пример

  См. в примере [IsBOF](#isbof).

##  <a name="onsetoptions"></a>  CRecordset::OnSetOptions

Вызывается, чтобы задать параметры (используется для выбора) для указанной инструкции ODBC.

```
virtual void OnSetOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Параметры

*HSTMT*<br/>
HSTMT, параметры которого задаются, инструкции ODBC.

### <a name="remarks"></a>Примечания

Вызовите `OnSetOptions` для задания параметров, (используется для выбора) для указанной инструкции ODBC. Чтобы задать начальные параметры для набора записей эта функция-член вызывается платформой. `OnSetOptions` Определяет источник данных поддерживает прокручиваемые курсоры и параллелизм курсоров и соответствующим образом задает параметры набора записей. (В то время как `OnSetOptions` используется для операций выбора, `OnSetUpdateOptions` используется для операций обновления.)

Переопределить `OnSetOptions` Чтобы установить параметры для драйвера или источника данных. Например, если источник данных поддерживает открытие монопольного доступа, может быть переопределено `OnSetOptions` преимуществами эту возможность.

Дополнительные сведения о курсорах см. в статье [ODBC](../../data/odbc/odbc-basics.md).

##  <a name="onsetupdateoptions"></a>  CRecordset::OnSetUpdateOptions

Вызывается для задания параметров (используется в центре обновления) для указанной инструкции ODBC.

```
virtual void OnSetUpdateOptions(HSTMT hstmt);
```

### <a name="parameters"></a>Параметры

*HSTMT*<br/>
HSTMT, параметры которого задаются, инструкции ODBC.

### <a name="remarks"></a>Примечания

Вызовите `OnSetUpdateOptions` для задания параметров, (используется в центре обновления) для указанной инструкции ODBC. Эта функция-член вызывается платформой, после создания HSTMT для обновления записей в наборе записей. (В то время как `OnSetOptions` используется для операций выбора, `OnSetUpdateOptions` используется для операций обновления.) `OnSetUpdateOptions` определяет источник данных поддерживает прокручиваемые курсоры и параллелизм курсоров и соответствующим образом задает параметры набора записей.

Переопределить `OnSetUpdateOptions` для задания параметров инструкции ODBC, прежде чем этот оператор используется для доступа к базе данных.

Дополнительные сведения о курсорах см. в статье [ODBC](../../data/odbc/odbc-basics.md).

##  <a name="open"></a>  CRecordset::Open

Получение таблицы или выполнять запрос, который представляет набор записей, открывает набор записей.

```
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,
    LPCTSTR lpszSQL = NULL,
    DWORD dwOptions = none);
```

### <a name="parameters"></a>Параметры

*nOpenType*<br/>
Примите значение по умолчанию, AFX_DB_USE_DEFAULT_TYPE или используйте одно из следующих значений из `enum OpenType`:

- `CRecordset::dynaset` Набор записей с двунаправленным письмом прокрутки. Членство и упорядочение набора записей определяются при открытии набора записей, но изменения, внесенные другими пользователями к значениям данных отображаются следующие операции выборки. Динамических подмножеств данных также называются набором записей в наборе.

- `CRecordset::snapshot` Статический набор записей с двунаправленным письмом прокрутки. Членство и упорядочение набора записей определяется при открытии набора записей; значения данных определяются при записи. Изменения, внесенные другими пользователями не видны, пока не будет закрыто и повторно открыть набор записей.

- `CRecordset::dynamic` Набор записей с двунаправленным письмом прокрутки. Изменения, внесенные другими пользователями членства, упорядочение и данные значения видны следующие операции выборки. Обратите внимание на то, что многие драйверы ODBC не поддерживают этот тип набора записей.

- `CRecordset::forwardOnly` Только для чтения записей с только прямую прокрутку.

   Для `CRecordset`, значение по умолчанию — `CRecordset::snapshot`. Значение по умолчанию механизм позволяет мастера Visual C++ для взаимодействия с и ODBC `CRecordset` и DAO `CDaoRecordset`, которые имеют различные значения по умолчанию.

Дополнительные сведения об этих типах записей см. в статье [записей (ODBC)](../../data/odbc/recordset-odbc.md). Дополнительные сведения см. в статье «С помощью блока и Прокручиваемые курсоры» в пакете Windows SDK.

> [!CAUTION]
>  Если запрашиваемый тип не поддерживается, то платформа создает исключение.

*lpszSQL*<br/>
Указатель на строку, содержащую одно из следующих:

- Указатель NULL.

- Имя таблицы.

- SQL **ВЫБЕРИТЕ** инструкции (при необходимости с помощью SQL **ГДЕ** или **ORDER BY** предложение).

- Объект **ВЫЗОВИТЕ** инструкцию, указав имя предопределенного запроса (хранимой процедуры). Следите за тем, которые не вставлять пробел между фигурными скобками и **ВЫЗОВИТЕ** ключевое слово.

Дополнительные сведения о данной строки см. в таблице и обсуждение ClassWizard его роль в разделе "Примечания".

> [!NOTE]
>  Порядок столбцов результирующего набора должен соответствовать порядку RFX или вызовы функции Bulk RFX в вашей [DoFieldExchange](#dofieldexchange) или [DoBulkFieldExchange](#dobulkfieldexchange) функции переопределения.

*dwOptions*<br/>
Битовая маска, в котором можно указать комбинацию значений, перечисленных ниже. Некоторые из них являются взаимоисключающими. Значение по умолчанию — **none**.

- `CRecordset::none` Параметры не заданы. Значение этого параметра является взаимоисключающим с другими значениями. По умолчанию, можно обновить набор записей с [изменить](#edit) или [удалить](#delete) и добавления новых записей с [AddNew](#addnew). Возможности обновления зависит от источника данных также на *nOpenType* вами параметр. Оптимизация для массового добавления не доступна. Выборка строк не реализована. Удаленные записи, не следует пропускать при навигации набор записей. Закладки недоступны. Проверка автоматического "грязных" поле реализуется.

- `CRecordset::appendOnly` Не разрешать `Edit` или `Delete` для объекта recordset. Разрешить `AddNew` только. Этот параметр является взаимоисключающим с `CRecordset::readOnly`.

- `CRecordset::readOnly` Откройте набор записей только для чтения. Этот параметр является взаимоисключающим с `CRecordset::appendOnly`.

- `CRecordset::optimizeBulkAdd` Используйте подготовленной инструкции SQL для оптимизации, добавив много записей за один раз. Применяется только в том случае, если вы не используете функции ODBC API `SQLSetPos` для обновления набора записей. Первого обновления, которое определяет, какие поля помечены как "грязный". Этот параметр является взаимоисключающим с `CRecordset::useMultiRowFetch`.

- `CRecordset::useMultiRowFetch` Реализуйте массовое получение строк, чтобы разрешить несколько строк, извлекаемых в одном fetch операции. Это является дополнительным, предназначенный для повышения производительности; Тем не менее блочный обмен полей записей по ClassWizard не поддерживается. Этот параметр является взаимоисключающим с `CRecordset::optimizeBulkAdd`. Обратите внимание, что при указании `CRecordset::useMultiRowFetch`, затем параметр `CRecordset::noDirtyFieldCheck` будет включен автоматически (двойной буферизации не будут доступны); на последовательным, параметр `CRecordset::useExtendedFetch` будет включен автоматически. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

- `CRecordset::skipDeletedRecords` Пропустите все удаленные записи, при переходе по набору записей. Это приводит к снижению производительности в определенных относительных выборки. Этот параметр не поддерживается на последовательным. При вызове метода [переместить](#move) с *nRows* параметра значение 0 и `CRecordset::skipDeletedRecords` параметр set, `Move` будет утверждать. Обратите внимание, что `CRecordset::skipDeletedRecords` аналогичен *упаковки драйвер*, означающее, удаленные строки удаляются из набора записей. Тем не менее если драйвер пакетов записей, затем он будет пропускать только те записи, которые можно удалить; он не будет пропускать записи, удаленные другими пользователями, пока открыт набор записей. `CRecordset::skipDeletedRecords` будет пропускать строки, удаленные другим пользователям.

- `CRecordset::useBookmarks` Использовать закладки в наборе записей, если поддерживается. Закладки замедляют работу извлечения данных, но также повысить производительность для перемещения в базе данных. Не является допустимым на последовательным. Дополнительные сведения см. в статье [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

- `CRecordset::noDirtyFieldCheck` Отключите автоматическое "грязных" поле проверки (двойной буферизации). Это улучшит производительность; Тем не менее, необходимо вручную пометить поля как черновой путем вызова `SetFieldDirty` и `SetFieldNull` функций-членов. Обратите внимание, что двойной буферизации в классе `CRecordset` аналогичен двойной буферизации в классе `CDaoRecordset`. Однако в `CRecordset`, вы не сможете включить двойную буферизацию в отдельные поля; его включить ее для всех полей или отключить для всех полей. Обратите внимание, что при использовании параметра `CRecordset::useMultiRowFetch`, затем `CRecordset::noDirtyFieldCheck` включается автоматически, однако `SetFieldDirty` и `SetFieldNull` не может использоваться для наборов записей, выборка строк.

- `CRecordset::executeDirect` Не используйте подготовленной инструкции SQL. Для повышения производительности, укажите этот параметр, если `Requery` функция-член не будет вызван.

- `CRecordset::useExtendedFetch` Реализуйте `SQLExtendedFetch` вместо `SQLFetch`. Эта возможность предназначена для реализации выборка строк на последовательным. При использовании параметра `CRecordset::useMultiRowFetch` последовательного наборов записей, затем `CRecordset::useExtendedFetch` будет включен автоматически.

- `CRecordset::userAllocMultiRowBuffers` Пользователь выделит буферов хранилища для данных. Используйте этот параметр в сочетании с `CRecordset::useMultiRowFetch` Если вы хотите выделить собственное хранилище; в противном случае платформа будет автоматически выделять хранилище. Дополнительные сведения см. в статье [набор записей: получение записей (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Обратите внимание, что при указании `CRecordset::userAllocMultiRowBuffers` без указания `CRecordset::useMultiRowFetch` приведет к утверждение, вызвавшее сбой.

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение `CRecordset` объект был успешно открыт; в противном случае — значение 0, если [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) (если вызывается) возвращает значение 0.

### <a name="remarks"></a>Примечания

Эта функция-член для выполнения запроса определяется набор записей, необходимо вызвать. Перед вызовом `Open`, необходимо создать объект recordset.

Этот набор записей соединение с источником данных зависит от того, при создании набора записей перед вызовом `Open`. Если передать [CDatabase](../../mfc/reference/cdatabase-class.md) объект recordset конструктор, который не был подключен к источнику данных, эта функция-член использует [GetDefaultConnect](#getdefaultconnect) попыток открытия объекта базы данных. Если передать значение NULL в конструктор набора записей, конструктор создает `CDatabase` объекта, и `Open` пытается подключиться объект базы данных. Дополнительные сведения о закрытием набора записей и соединения в этих различных условиях, см. в разделе [закрыть](#close).

> [!NOTE]
>  Доступ к источнику данных с помощью `CRecordset` объект всегда является общим. В отличие от `CDaoRecordset` , нельзя использовать `CRecordset` объект, чтобы открыть источник данных с монопольным доступом.

При вызове `Open`, запрос, который обычно SQL **ВЫБЕРИТЕ** инструкция, выбирает записей на основе критериев, показано в следующей таблице.

|Значение параметра lpszSQL|Выбрано записей определяются|Пример|
|------------------------------------|----------------------------------------|-------------|
|NULL|Строка, возвращаемая `GetDefaultSQL`.||
|Имя таблицы SQL|Все столбцы из списка таблиц в `DoFieldExchange` или `DoBulkFieldExchange`.|`"Customer"`|
|Имя предопределенного запроса (хранимая процедура)|Столбцы, которые запрос, определенный для возврата.|`"{call OverDueAccts}"`|
|**ВЫБЕРИТЕ** список столбцов **FROM** список таблиц|Указанные столбцы из указанной таблицы.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|

> [!CAUTION]
>  Будьте осторожны, не вставляйте лишних пробелов в строке SQL. Например, если вставить пробел между фигурными скобками и **вызвать** ключевое слово, MFC будут неправильно интерпретировать строку как имя таблицы SQL и включить его в **ВЫБЕРИТЕ** инструкцию, которая приведет к исключения. Аналогичным образом, если ваш предопределенного запроса используется выходной параметр, не вставляйте пробелы между фигурными скобками и '' символ. Наконец, не нужно вставить пробел перед фигурную скобку в **вызвать** инструкции или до **ВЫБЕРИТЕ** ключевое слово в **ВЫБЕРИТЕ** инструкции.

Стандартные действия является передача значения NULL для `Open`; в этом случае `Open` вызовы [GetDefaultSQL](#getdefaultsql). Если вы используете производный `CRecordset` класса `GetDefaultSQL` предоставляет имена таблицы, указанной в ClassWizard. Вместо этого можно указать другие сведения в `lpszSQL` параметра.

Все передаваемые `Open` создает окончательной строки SQL для запроса (строка может содержать SQL **ГДЕ** и **ORDER BY** добавляемой в конце предложения `lpszSQL` строки, которые Вы передали), а затем выполняет запрос. Сконструированная строка можно просмотреть путем вызова [GetSQL](#getsql) после вызова метода `Open`. Дополнительные сведения о том, как набор записей создает инструкцию SQL и выбирает записи, см. в статье [набор записей: принцип наборы записей выберите записей (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).

Элементами данных полей класса набора записей привязанные к столбцам выбранных данных. Если возвращаются все записи, первая запись становится текущей записи.

Если вы хотите задать параметры для набора записей, таких как фильтр или сортировку, укажите их после создания объекта набора записей, но перед вызовом метода `Open`. Если вы хотите обновить записи в наборе записей после набор записей уже открыт, вызовите [Requery](#requery).

Дополнительные сведения, включая дополнительные примеры см. в статьях [записей (ODBC)](../../data/odbc/recordset-odbc.md), [набор записей: принцип наборы записей выберите записей (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md), и [набор записей: Создание и закрытие Наборы записей (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).

### <a name="example"></a>Пример

В следующих примерах кода показано разные формы `Open` вызова.

[!code-cpp[NVC_MFCDatabase#16](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]

##  <a name="refreshrowset"></a>  CRecordset::RefreshRowset

Обновляет данные и состояние для строки в текущем наборе строк.

```
void RefreshRowset(
    WORD wRow,
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Параметры

*wRow*<br/>
От единицы позиция строки в текущем наборе строк. Это значение может изменяться от нуля до размер набора строк.

*wLockType*<br/>
Значение, указывающее, как заблокировать ее после его обновления. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

Если передается нулевое значение для *wRow*, то каждая строка в наборе строк будут обновляться.

Для использования `RefreshRowset`, вы должны реализованы выборка строк, указав `CRecordset::useMulitRowFetch` в диалоговом окне [откройте](#open) функция-член.

`RefreshRowset` вызывает функцию ODBC API `SQLSetPos`. *WLockType* параметр указывает состояние блокировки строки после `SQLSetPos` выполнен. В следующей таблице описаны возможные значения для *wLockType*.

|wLockType|Описание|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (значение по умолчанию)|Драйвер или источник данных гарантирует, что строка является в то же состояние заблокирован или разблокирован, как было до `RefreshRowset` был вызван.|
|SQL_LOCK_EXCLUSIVE|Драйвер или источник данных исключительно блокирует строку. Не все источники данных поддерживают этот тип блокировки.|
|SQL_LOCK_UNLOCK|Драйвер или источник данных снимает блокировку строки. Не все источники данных поддерживают этот тип блокировки.|

Дополнительные сведения о `SQLSetPos`, см. в Windows SDK. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="requery"></a>  Метод CRecordset::Requery

Перестраивает (обновлений) набор записей.

```
virtual BOOL Requery();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если набор записей была успешно перестроена; в противном случае 0.

### <a name="remarks"></a>Примечания

Если возвращаются все записи, первая запись становится текущей записи.

В порядке для набора записей в соответствии с добавления и удаления, которые вы или другим пользователям больше всего к источнику данных, необходимо перестроить набор записей путем вызова `Requery`. Если набор записей является динамическим подмножеством данных, автоматически отражает обновлений, которые вы или другие пользователи его существующие записи (но не дополнения). Если набор записей является моментальным снимком, необходимо вызвать метод `Requery` для отражения изменений, с другими пользователями, а также добавления и удаления.

Для подмножества или моментального снимка вызовите `Requery` любое время, необходимо перестроить набор записей, с помощью нового фильтра или сортировки или новые значения параметров. Задайте свойства нового фильтра или сортировки, задавая новые значения для `m_strFilter` и `m_strSort` перед вызовом `Requery`. Задайте новые параметры, задавая новые значения членов данных параметра перед вызовом `Requery`. Если фильтрация и сортировка строк не изменились, можно повторно использовать в запросе, которая повышает производительность.

Если произошел сбой попытки повторного построения recordset, закрывается набор записей. Перед вызовом метода `Requery`, можно определить, является ли набор записей можно опросить путем вызова `CanRestart` функция-член. `CanRestart` не гарантирует, что `Requery` будет выполнена успешно.

> [!CAUTION]
>  Вызовите `Requery` только после вызова [откройте](#open).

### <a name="example"></a>Пример

В этом примере перестраивается набор записей, чтобы применить другой порядок сортировки.

[!code-cpp[NVC_MFCDatabase#29](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]

##  <a name="setabsoluteposition"></a>  CRecordset::SetAbsolutePosition

Устанавливает набор записей на запись, соответствующая указанный номер.

```
void SetAbsolutePosition(long nRows);
```

### <a name="parameters"></a>Параметры

*nRows*<br/>
С единицы порядковый номер для текущей записи в наборе записей.

### <a name="remarks"></a>Примечания

`SetAbsolutePosition` Перемещает указатель текущей записи, исходя из этого порядковый номер.

> [!NOTE]
>  Эта функция-член не допускается для последовательным.

Для набора записей ODBC абсолютное положение параметр 1 относится к первой записи в наборе записей; значение 0 указывает позицию начала файла (записи BOF).

Можно также передать отрицательные значения для `SetAbsolutePosition`. В этом случае позиция набора записей вычисляется из конца набора. Например `SetAbsolutePosition( -1 )` перемещает указатель текущей записи к последней записи в наборе записей.

> [!NOTE]
>  Абсолютное положение не предназначен для использования в качестве символов-заместителей номер записи. Закладки-это по-прежнему рекомендуемый способ сохранения и возврата заданной позиции, с момента изменения позиции записи при удалении предыдущего записей. Кроме того, вы не может быть уверенным, что определенной записи будет же абсолютное положение, если набор записей является повторно создан так, как порядок отдельных записей в наборе записей не гарантируется, если она создается с помощью инструкции SQL с помощью **ORDER BY** предложение.

Дополнительные сведения о перемещении по набору записей и создает закладки, см. в статьях [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) и [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).

##  <a name="setbookmark"></a>  CRecordset::SetBookmark

Устанавливает набор записей на запись, содержащую указанную закладку.

```
void SetBookmark(const CDBVariant& varBookmark);
```

### <a name="parameters"></a>Параметры

*varBookmark*<br/>
Ссылку на [CDBVariant](../../mfc/reference/cdbvariant-class.md) объект, содержащий значение для определенной записи.

### <a name="remarks"></a>Примечания

Чтобы определить, поддерживаются ли закладки для объекта recordset, вызовите [CanBookmark](#canbookmark). Чтобы сделать закладки доступным, если они поддерживаются, необходимо задать `CRecordset::useBookmarks` в диалоговом окне *dwOptions* параметр [откройте](#open) функция-член.

> [!NOTE]
>  Если закладки-это неподдерживаемый или недоступен, вызов метода `SetBookmark` приведет к возникновению исключения. Закладки не поддерживаются в последовательным.

Чтобы сначала получить закладки для текущей записи, вызовите [GetBookmark](#getbookmark), который сохраняет значения закладки для `CDBVariant` объекта. Позже можно вернуться к этой записи, вызвав `SetBookmark` с использованием значения сохраненную закладку.

> [!NOTE]
>  После определенных операций набор записей, следует проверить сохраняемость закладку перед вызовом `SetBookmark`. Например, если получить закладки с `GetBookmark` , а затем вызвать `Requery`, закладки больше не может быть допустимым. Вызовите [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) для проверки, можно ли безопасно вызов `SetBookmark`.

Дополнительные сведения о закладок и навигации набор записей, см. в статьях [Recordset: закладки и абсолютные позиции (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) и [набор записей: прокрутка (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).

##  <a name="setfielddirty"></a>  CRecordset::SetFieldDirty

Флаги элемента данных поля в наборе записей, изменяются или как неизмененные.

```
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Содержит адрес элемента данных поля в наборе записей или значение NULL. Если значение равно NULL, помечаются все поля элементов данных в наборе записей. (C++ NULL не является таким же, как значение Null в терминологии связанных баз данных, что означает «предложений having без значения.»)

*bDirty*<br/>
Значение TRUE, если элемент данных полю будет помечен как «грязный» (измененные). В противном случае значение FALSE, если элемент данных полю будет помечен как «чистые» (без изменений).

### <a name="remarks"></a>Примечания

Пометка полей как неизмененные гарантирует поля не обновляется и создает меньше трафика SQL.

> [!NOTE]
>  Эта функция-член не применим на наборы записей, в которых используется выборка строк. Если вы реализовали выборка строк, затем `SetFieldDirty` приведет к утверждение, вызвавшее сбой. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Метки framework изменить поля элементов данных, чтобы убедиться, что они записываются в запись в источнике данных с помощью механизма полями записей (RFX) exchange. Изменение значения поля обычно устанавливает для поля "грязных" автоматически, поэтому редко нужно вызывать `SetFieldDirty` самостоятельно, но иногда может потребоваться убедиться, что столбцы будут будут явно обновлены или вставлены независимо от того, какое значение в поле данных член.

> [!CAUTION]
>  Вызовите эту функцию-член, только после вызова [изменить](#edit) или [AddNew](#addnew).

Использование значения NULL, первый аргумент функции будет применяться только к функции `outputColumn` поля, не `param` поля. Например вызов

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

будет только при задании `outputColumn` поля NULL; `param` поля не будут затронуты.

Для работы на `param` поля, необходимо указать фактический адрес лица, `param` для работы, такие как:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Это означает, что нельзя задать все `param` поля значение NULL, как и с помощью `outputColumn` поля.

##  <a name="setfieldnull"></a>  CRecordset::SetFieldNull

Флаги элемента данных поля в наборе записей, как Null (в частности, имеющая значение не) или как отличное от Null.

```
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```

### <a name="parameters"></a>Параметры

*PV*<br/>
Содержит адрес элемента данных поля в наборе записей или значение NULL. Если значение равно NULL, помечаются все поля элементов данных в наборе записей. (C++ NULL не является таким же, как значение Null в терминологии связанных баз данных, что означает «предложений having без значения.»)

*bNull*<br/>
Ненулевое значение, если элемент данных поля помечаются как имеющие нет значения (Null). В противном случае — 0, если элемент данных поля будет помечен как отличное от Null.

### <a name="remarks"></a>Примечания

При добавлении новой записи в набор записей, все поля элементов данных изначально присвоено значение Null и помечен как «грязный» (измененные). При извлечении записи из источника данных, ее столбцы уже имеют значения либо равны Null.

> [!NOTE]
>  Не вызывайте эту функцию-член в наборы записей, в которых используется выборка строк. Если вы реализовали выборка строк, при вызове метода `SetFieldNull` приводит утверждение, вызвавшее сбой. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Если требуется специально назначения поля текущей записи как не имеющий значение, вызов `SetFieldNull` с *bNull* присвоено значение TRUE, чтобы пометить его как Null. Если ранее был помечен поле значение Null, а теперь нужно ему присваивается значение, просто задайте его новое значение. Необходимо удалить флаг Null с помощью `SetFieldNull`. Чтобы определить, разрешено ли поле иметь значение Null, вызовите `IsFieldNullable`.

> [!CAUTION]
>  Вызовите эту функцию-член, только после вызова [изменить](#edit) или [AddNew](#addnew).

Использование значения NULL, первый аргумент функции будет применяться только к функции `outputColumn` поля, не `param` поля. Например вызов

[!code-cpp[NVC_MFCDatabase#26](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]

будет только при задании `outputColumn` поля NULL; `param` поля не будут затронуты.

Для работы на `param` поля, необходимо указать фактический адрес лица, `param` для работы, такие как:

[!code-cpp[NVC_MFCDatabase#27](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]

Это означает, что нельзя задать все `param` поля значение NULL, как и с помощью `outputColumn` поля.

> [!NOTE]
>  При задании параметров значение NULL, вызов `SetFieldNull` прежде, чем набор записей является открытый результаты в утверждение. В этом случае вызов [члена SetParamNull](#setparamnull).

`SetFieldNull` реализуется с помощью [DoFieldExchange](#dofieldexchange).

##  <a name="setlockingmode"></a>  CRecordset::SetLockingMode

Задает режим блокировки «оптимистичный» блокировка (по умолчанию) или «пессимистической» блокировки. Определяет, как блокировки записей для обновления.

```
void SetLockingMode(UINT nMode);
```

### <a name="parameters"></a>Параметры

*nMode*<br/>
Содержит одно из следующих значений из `enum LockMode`:

- `optimistic` Оптимистическая блокировка блокировки записи, которая обновляется только во время вызова `Update`.

- `pessimistic` Пессимистической блокировки запись блокируется сразу же `Edit` вызывается и поддерживает заблокирована до `Update` завершения вызова или переместить в новую запись.

### <a name="remarks"></a>Примечания

Вызовите эту функцию-член, если вам нужно указать, какой из двух стратегий блокировки записей, набор записей используется для обновления. По умолчанию используется режим блокировки набора записей `optimistic`. Его можно изменить на более осторожность `pessimistic` стратегия блокировки. Вызовите `SetLockingMode` после создания и открытия объекта набора записей, но перед вызовом метода `Edit`.

##  <a name="setparamnull"></a>  CRecordset::SetParamNull

Флаги параметра, отличное от Null или Null (в частности, имеющая значение не).

```
void SetParamNull(
    int nIndex,
    BOOL bNull = TRUE);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Отсчитываемый с нуля индекс параметра.

*bNull*<br/>
Если значение TRUE (значение по умолчанию), параметр помечен как Null. В противном случае параметр помечен как отличное от Null.

### <a name="remarks"></a>Примечания

В отличие от [метод SetFieldNull](#setfieldnull), можно вызвать `SetParamNull` прежде, чем вы открыли набор записей.

`SetParamNull` обычно используется с предопределенные запросы (хранимые процедуры).

##  <a name="setrowsetcursorposition"></a>  CRecordset::SetRowsetCursorPosition

Перемещает курсор в строку в текущем наборе строк.

```
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```

### <a name="parameters"></a>Параметры

*wRow*<br/>
От единицы позиция строки в текущем наборе строк. Это значение находится в диапазоне от 1 до размера набора строк.

*wLockType*<br/>
Значение, определяющее способ блокировки строки, после его обновления. Дополнительные сведения см. в разделе "Заметки".

### <a name="remarks"></a>Примечания

При реализации групповой выборки строк, записи извлекаются путем наборы строк, где текущей записи в первой записи в извлеченных строк. Чтобы сделать текущей записи еще одну запись в наборе строк, вызвать `SetRowsetCursorPosition`. Например, можно объединить `SetRowsetCursorPosition` с [GetFieldValue](#getfieldvalue) функция-член для динамического извлечения данных из любой записи набора записей.

Для использования `SetRowsetCursorPosition`, вы должны реализованы выборка строк, указав `CRecordset::useMultiRowFetch` параметр *dwOptions* параметр в [откройте](#open) функция-член.

`SetRowsetCursorPosition` вызывает функцию ODBC API `SQLSetPos`. *WLockType* параметр указывает состояние блокировки строки после `SQLSetPos` выполнен. В следующей таблице описаны возможные значения для *wLockType*.

|wLockType|Описание|
|---------------|-----------------|
|SQL_LOCK_NO_CHANGE (значение по умолчанию)|Драйвер или источник данных гарантирует, что строка является в то же состояние заблокирован или разблокирован, как было до `SetRowsetCursorPosition` был вызван.|
|SQL_LOCK_EXCLUSIVE|Драйвер или источник данных исключительно блокирует строку. Не все источники данных поддерживают этот тип блокировки.|
|SQL_LOCK_UNLOCK|Драйвер или источник данных снимает блокировку строки. Не все источники данных поддерживают этот тип блокировки.|

Дополнительные сведения о `SQLSetPos`, см. в Windows SDK. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="setrowsetsize"></a>  CRecordset::SetRowsetSize

Указывает количество записей, которые вы хотите получить во время выборки.

```
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```

### <a name="parameters"></a>Параметры

*dwNewRowsetSize*<br/>
Число строк во время операции выборки.

### <a name="remarks"></a>Примечания

Это виртуальная функция-член указывает, сколько строк, извлекаемых во время одной выборки при использовании массовой выборке строк. Чтобы реализовать выборка строк, необходимо задать `CRecordset::useMultiRowFetch` в диалоговом окне *dwOptions* параметр [откройте](#open) функция-член.

> [!NOTE]
>  Вызов `SetRowsetSize` без реализации массовой выборки строк приведет к утверждение, вызвавшее сбой.

Вызовите `SetRowsetSize` перед вызовом метода `Open` для начальной установки размера набора строк для набора записей. Размер набора строк по умолчанию, при реализации выборка строк — 25.

> [!NOTE]
>  Соблюдайте осторожность при вызове `SetRowsetSize`. Если вручную при выделении хранилища для данных (как указано `CRecordset::userAllocMultiRowBuffers` параметр dwOptions параметра в `Open`), следует проверить, требуется ли перераспределять буфер хранения после вызова метода `SetRowsetSize`, но прежде чем Выполните никаких операций перемещения курсора.

Чтобы получить текущее значение для размера набора строк, вызвать [GetRowsetSize](#getrowsetsize).

Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

##  <a name="update"></a>  CRecordset::Update

Завершает `AddNew` или `Edit` операции путем сохранения новых или измененных данных в источнике данных.

```
virtual BOOL Update();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если одна запись успешно обновлен; в противном случае — 0, если столбцы не были изменены. Если записи не были обновлены, или если более чем одна запись была обновлена, создается исключение. Также исключение для любой другой ошибки в источнике данных.

### <a name="remarks"></a>Примечания

Это функция-член вызывается после вызова [AddNew](#addnew) или [изменить](#edit) функция-член. Этот вызов необходим для завершения `AddNew` или `Edit` операции.

> [!NOTE]
>  Если вы реализовали выборка строк, нельзя вызывать `Update`. Это приведет к утверждение, вызвавшее сбой. Несмотря на то что класс `CRecordset` не предоставляет механизм для обновления пакетов строк данных, можно создавать собственные функции с помощью функции ODBC API `SQLSetPos`. Дополнительные сведения о массовой выборке строк см. в статье [Набор записей: пакетная выборка строк (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).

Оба `AddNew` и `Edit` Подготовка буфера редактирования, в котором размещается добавленных или измененных данных для сохранения в источнике данных. `Update` сохраняет данные. Обновляются только поля, помеченные или обнаружено как измененный.

Если источник данных поддерживает транзакции, можно сделать `Update` вызова (и его соответствующее `AddNew` или `Edit` вызовите) частью транзакции. Дополнительные сведения о транзакциях см. в статье [транзакции (ODBC)](../../data/odbc/transaction-odbc.md).

> [!CAUTION]
>  При вызове метода `Update` без предварительного вызова либо `AddNew` или `Edit`, `Update` вызывает `CDBException`. При вызове метода `AddNew` или `Edit`, необходимо вызвать `Update` перед вызовом метода `Move` операции или до закрытия соединения с источником данных или набора записей. В противном случае изменения будут утеряны без уведомления.

Дополнительные сведения об обработке `Update` сбои, см. в статье [набор записей: принцип наборы записей обновления записей (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).

### <a name="example"></a>Пример

См. в статье [транзакции: выполнение транзакции в наборе записей (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDatabase](../../mfc/reference/cdatabase-class.md)<br/>
[Класс CRecordView](../../mfc/reference/crecordview-class.md)
