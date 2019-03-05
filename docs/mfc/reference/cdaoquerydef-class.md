---
title: Класс CDaoQueryDef
ms.date: 11/04/2016
f1_keywords:
- CDaoQueryDef
- AFXDAO/CDaoQueryDef
- AFXDAO/CDaoQueryDef::CDaoQueryDef
- AFXDAO/CDaoQueryDef::Append
- AFXDAO/CDaoQueryDef::CanUpdate
- AFXDAO/CDaoQueryDef::Close
- AFXDAO/CDaoQueryDef::Create
- AFXDAO/CDaoQueryDef::Execute
- AFXDAO/CDaoQueryDef::GetConnect
- AFXDAO/CDaoQueryDef::GetDateCreated
- AFXDAO/CDaoQueryDef::GetDateLastUpdated
- AFXDAO/CDaoQueryDef::GetFieldCount
- AFXDAO/CDaoQueryDef::GetFieldInfo
- AFXDAO/CDaoQueryDef::GetName
- AFXDAO/CDaoQueryDef::GetODBCTimeout
- AFXDAO/CDaoQueryDef::GetParameterCount
- AFXDAO/CDaoQueryDef::GetParameterInfo
- AFXDAO/CDaoQueryDef::GetParamValue
- AFXDAO/CDaoQueryDef::GetRecordsAffected
- AFXDAO/CDaoQueryDef::GetReturnsRecords
- AFXDAO/CDaoQueryDef::GetSQL
- AFXDAO/CDaoQueryDef::GetType
- AFXDAO/CDaoQueryDef::IsOpen
- AFXDAO/CDaoQueryDef::Open
- AFXDAO/CDaoQueryDef::SetConnect
- AFXDAO/CDaoQueryDef::SetName
- AFXDAO/CDaoQueryDef::SetODBCTimeout
- AFXDAO/CDaoQueryDef::SetParamValue
- AFXDAO/CDaoQueryDef::SetReturnsRecords
- AFXDAO/CDaoQueryDef::SetSQL
- AFXDAO/CDaoQueryDef::m_pDAOQueryDef
- AFXDAO/CDaoQueryDef::m_pDatabase
helpviewer_keywords:
- CDaoQueryDef [MFC], CDaoQueryDef
- CDaoQueryDef [MFC], Append
- CDaoQueryDef [MFC], CanUpdate
- CDaoQueryDef [MFC], Close
- CDaoQueryDef [MFC], Create
- CDaoQueryDef [MFC], Execute
- CDaoQueryDef [MFC], GetConnect
- CDaoQueryDef [MFC], GetDateCreated
- CDaoQueryDef [MFC], GetDateLastUpdated
- CDaoQueryDef [MFC], GetFieldCount
- CDaoQueryDef [MFC], GetFieldInfo
- CDaoQueryDef [MFC], GetName
- CDaoQueryDef [MFC], GetODBCTimeout
- CDaoQueryDef [MFC], GetParameterCount
- CDaoQueryDef [MFC], GetParameterInfo
- CDaoQueryDef [MFC], GetParamValue
- CDaoQueryDef [MFC], GetRecordsAffected
- CDaoQueryDef [MFC], GetReturnsRecords
- CDaoQueryDef [MFC], GetSQL
- CDaoQueryDef [MFC], GetType
- CDaoQueryDef [MFC], IsOpen
- CDaoQueryDef [MFC], Open
- CDaoQueryDef [MFC], SetConnect
- CDaoQueryDef [MFC], SetName
- CDaoQueryDef [MFC], SetODBCTimeout
- CDaoQueryDef [MFC], SetParamValue
- CDaoQueryDef [MFC], SetReturnsRecords
- CDaoQueryDef [MFC], SetSQL
- CDaoQueryDef [MFC], m_pDAOQueryDef
- CDaoQueryDef [MFC], m_pDatabase
ms.assetid: 9676a4a3-c712-44d4-8c5d-d1cc78288d3a
ms.openlocfilehash: 08fb2909a4fd2e5bda3dfc63d19224a515c7c699
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57283648"
---
# <a name="cdaoquerydef-class"></a>Класс CDaoQueryDef

Представляет определение запроса или QueryDef, как правило, сохраненный в базе данных.

## <a name="syntax"></a>Синтаксис

```
class CDaoQueryDef : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[CDaoQueryDef::CDaoQueryDef](#cdaoquerydef)|Создает объект `CDaoQueryDef`. Затем вызовите метод `Open` или `Create`, в зависимости от потребностей.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[CDaoQueryDef::Append](#append)|Добавляет querydef querydefs-коллекция базы данных как сохраненный запрос.|
|[CDaoQueryDef::CanUpdate](#canupdate)|Возвращает ненулевое значение, если запрос можно обновить базу данных.|
|[CDaoQueryDef::Close](#close)|Закрывает объект querydef. Удаляет этот объект C++ после завершения работы с его.|
|[CDaoQueryDef::Create](#create)|Создает базовый объект querydef DAO. Использовать в качестве временного запроса или вызова querydef `Append` сохранить его в базе данных.|
|[CDaoQueryDef::Execute](#execute)|Выполняет запрос, определенный объектом querydef.|
|[CDaoQueryDef::GetConnect](#getconnect)|Возвращает строку подключения, связанную с querydef. Строка подключения определяет источник данных. (Для SQL передаваемых запросов только; в противном случае пустая строка.)|
|[CDaoQueryDef::GetDateCreated](#getdatecreated)|Возвращает дату создания сохраненного запроса.|
|[CDaoQueryDef::GetDateLastUpdated](#getdatelastupdated)|Возвращает дату последнего обновления сохраненного запроса.|
|[CDaoQueryDef::GetFieldCount](#getfieldcount)|Возвращает количество полей, определенных querydef.|
|[CDaoQueryDef::GetFieldInfo](#getfieldinfo)|Возвращает сведения о указанного поля, определенные в запросе.|
|[CDaoQueryDef::GetName](#getname)|Возвращает имя querydef.|
|[CDaoQueryDef::GetODBCTimeout](#getodbctimeout)|Возвращает значение времени ожидания, используемые ODBC (для запроса ODBC) при выполнении querydef. Это определяет продолжительность разрешить до завершения действия запроса.|
|[CDaoQueryDef::GetParameterCount](#getparametercount)|Возвращает количество параметров, определенных для запроса.|
|[CDaoQueryDef::GetParameterInfo](#getparameterinfo)|Возвращает сведения о указанного параметра в запрос.|
|[CDaoQueryDef::GetParamValue](#getparamvalue)|Возвращает значение указанного параметра в запрос.|
|[CDaoQueryDef::GetRecordsAffected](#getrecordsaffected)|Возвращает количество записей, затронутых запросом.|
|[CDaoQueryDef::GetReturnsRecords](#getreturnsrecords)|Возвращает ненулевое значение, если запрос, определенный с querydef возвращает записи.|
|[CDaoQueryDef::GetSQL](#getsql)|Возвращает строку SQL, определяющую запрос, определенный с querydef.|
|[CDaoQueryDef::GetType](#gettype)|Возвращает тип запроса: удаление, обновление, добавление, создание таблицы и т. д.|
|[CDaoQueryDef::IsOpen](#isopen)|Возвращает ненулевое значение, если querydef открыт и может быть выполнено.|
|[CDaoQueryDef::Open](#open)|Открытие существующего querydef, хранящихся в базе данных querydefs-коллекция.|
|[CDaoQueryDef::SetConnect](#setconnect)|Задает строку подключения для запроса к серверу на источник данных ODBC.|
|[CDaoQueryDef::SetName](#setname)|Задает имя сохраненного запроса, заменив имя используется при создании querydef.|
|[CDaoQueryDef::SetODBCTimeout](#setodbctimeout)|Задает значение времени ожидания, используемые ODBC (для запроса ODBC) при выполнении querydef.|
|[CDaoQueryDef::SetParamValue](#setparamvalue)|Задает значение указанного параметра в запрос.|
|[CDaoQueryDef::SetReturnsRecords](#setreturnsrecords)|Определяет, возвращает ли querydef записей. Установка этого атрибута в значение TRUE допустимо только для запросов к серверу.|
|[CDaoQueryDef::SetSQL](#setsql)|Задает, указывающее запрос, определенный с querydef SQL-строку.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание:|
|----------|-----------------|
|[CDaoQueryDef::m_pDAOQueryDef](#m_pdaoquerydef)|Указатель на интерфейс OLE для базового объекта querydef DAO.|
|[CDaoQueryDef::m_pDatabase](#m_pdatabase)|Указатель на `CDaoDatabase` объект, с которым связан querydef. Querydef может быть сохранен в базе данных, или нет.|

## <a name="remarks"></a>Примечания

Querydef — это объект доступа данных, который содержит инструкцию SQL, которая описывает запрос и его свойства, такие как «Дата создания» и «Время ожидания ODBC». Можно также создать временный querydef объекты без сохранения, но это удобно и гораздо эффективнее — сохранять часто повторно использовать запросы в базе данных. Объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объект поддерживает набор данных с названием querydefs-коллекция, содержащий его сохраненного querydefs.

> [!NOTE]
>  Классы баз данных DAO, отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Вы можете по-прежнему доступ к источникам данных ODBC с помощью классов DAO. В общем случае классы MFC, в зависимости от DAO обладают большими возможностями, чем классы MFC на основе ODBC; классы на основе DAO можно получить доступ к данных, в том числе через драйверы ODBC, с помощью собственных компонент database engine. Классы на основе DAO также поддерживают операции языка описания данных DDL, например добавление таблиц через классы, не нужно звонить DAO напрямую.

## <a name="usage"></a>Использование

С помощью querydef объектов либо для работы с существующим сохраненный запрос или для создания нового сохраненного запроса или временных запросов:

1. В любом случае сначала создать `CDaoQueryDef` объекта, предоставляя указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) к которому принадлежит запрос.

1. Затем выполните следующие действия, в зависимости от желаемого.

   - Чтобы использовать существующий сохраненный запрос, вызовите объекта querydef [откройте](#open) функция-член, указав имя сохраненного запроса.

   - Чтобы создать новый сохраненный запрос, вызовите объекта querydef [создать](#create) функция-член, указав имя запроса. Затем вызовите [Append](#append) сохранить запрос путем добавления его к querydefs-коллекция базы данных. `Create` Помещает querydef в открытом состоянии, поэтому после вызова метода `Create` не следует вызывать `Open`.

   - Чтобы создать временный querydef, вызовите `Create`. Передайте пустую строку для имени запроса. Не вызывайте `Append`.

После завершения использования объекта querydef, вызовите его [закрыть](#close) члена функции; затем удалите объект querydef.

> [!TIP]
>  — Это самый простой способ создать сохраненные запросы для их создания и сохранения их в базе данных с помощью Microsoft Access. Затем можно открыть и использовать их в коде MFC.

## <a name="purposes"></a>В целях

Можно использовать объект querydef для любого из следующих целей:

- Для создания `CDaoRecordset` объекта

- Для вызова объекта `Execute` функция-член непосредственное выполнение запроса или запроса к серверу

Можно использовать объект querydef для любого типа запроса, включая select, действие, перекрестного, удаление, обновление, добавление, создание таблицы, определение данных, к серверу SQL, union и массовые запросы. Тип запроса определяется по содержимому, указываемое в инструкции SQL. Сведения о типах запросов см. в разделе `Execute` и [GetType](#gettype) функций-членов. Наборы записей обычно используются для возвращения строк запросов, обычно их с помощью **ВЫБЕРИТЕ... ИЗ** ключевые слова. `Execute` Чаще всего используется для массовых операций. Дополнительные сведения см. в разделе [Execute](#execute) и [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

## <a name="querydefs-and-recordsets"></a>Querydefs и наборами записей

Использовать для создания объекта querydef `CDaoRecordset` объекта, обычно создании или открытии querydef, как описано выше. Затем создайте объект набора записей, указателю на объект querydef при вызове [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Querydef, указываемые должны находиться в открытом состоянии. Дополнительные сведения см. в разделе класса [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Querydef нельзя использовать для создания набора записей (чаще всего используют для querydef), если он находится в открытом состоянии. Поместить querydef в открытом состоянии с помощью вызова `Open` или `Create`.

## <a name="external-databases"></a>Внешние базы данных

Объекты QueryDef являются предпочтительным способом для использования собственного диалект SQL двигателя внешней базы данных. Например можно создать запрос Transact SQL (как указано в Microsoft SQL Server) и сохраните его в объект querydef. Если вам нужно использовать SQL-запрос, не зависит от базы данных Microsoft Jet, необходимо указать строку подключения, который указывает на внешний источник данных. Запросы со строками соединения обойти ядро базы данных и передает запрос непосредственно на сервер внешней базы данных для использования.

> [!TIP]
>  Предпочтительный способ работы с таблицами ODBC является подключите их к Microsoft Jet (. База данных MDB).

Дополнительные сведения см в разделах «QueryDef объект», «Querydefs-коллекция» и «CdbDatabase объект» в пакете SDK DAO.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDaoQueryDef`

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

##  <a name="append"></a>  CDaoQueryDef::Append

Вызовите эту функцию-член, после вызова метода [создать](#create) для создания нового объекта querydef.

```
virtual void Append();
```

### <a name="remarks"></a>Примечания

`Append` сохраняет querydef в базе данных путем добавления объекта к querydefs-коллекция базы данных. Querydef можно использовать в качестве временного объекта без добавления ее, но если требуется сохранить, необходимо вызвать `Append`.

При попытке добавить объект временного querydef, MFC вызывает исключение типа [CDaoException](../../mfc/reference/cdaoexception-class.md).

##  <a name="canupdate"></a>  CDaoQueryDef::CanUpdate

Вызывайте эту функцию члена, чтобы определить, можно ли изменить querydef, например изменить его имя или строка SQL.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если вы можете изменить querydef; в противном случае 0.

### <a name="remarks"></a>Примечания

Вы можете изменить querydef, если:

- Он не зависит от базы данных, которая открыта только для чтения.

- У вас обновление разрешений для базы данных.

   Это зависит от того, реализуется ли функции безопасности. MFC не обеспечивает поддержку для обеспечения безопасности; необходимо реализовать его самостоятельно, вызов DAO напрямую или с помощью Microsoft Access. См. в разделе «Разрешения свойство» в справке DAO.

##  <a name="cdaoquerydef"></a>  CDaoQueryDef::CDaoQueryDef

Создает объект `CDaoQueryDef`.

```
CDaoQueryDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Параметры

*pDatabase*<br/>
Указатель на открытый [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.

### <a name="remarks"></a>Примечания

Объект может представлять существующего querydef, хранящихся в querydefs-коллекция базы данных, запроса для сохранения в коллекции или временных запросов, не должен быть сохранен. Следующий шаг зависит от типа querydef:

- Если объект представляет существующего querydef, вызвать для объекта [откройте](#open) функция-член для его инициализации.

- Если объект представляет новый querydef должен быть сохранен, вызвать для объекта [создать](#create) функция-член. Это добавляет объект querydefs-коллекция базы данных. Затем вызовите `CDaoQueryDef` функции-члены для задания атрибутов объекта. Наконец, вызовите [Append](#append).

- Если объект представляет временной querydef (не должен быть сохранен в базе данных), вызовите `Create`, передав пустую строку для имени запроса. После вызова метода `Create`, инициализировать querydef путем непосредственной настройки его атрибуты. Не вызывайте `Append`.

Чтобы задать атрибуты querydef, можно использовать [SetName](#setname), [SetSQL](#setsql), [SetConnect](#setconnect), [SetODBCTimeout](#setodbctimeout)и [SetReturnsRecords](#setreturnsrecords) функций-членов.

Когда вы закончите с объектом querydef, вызовите его [закрыть](#close) функция-член. Если у вас есть указатель на querydef, используйте **удалить** оператор для уничтожения объекта C++.

##  <a name="close"></a>  CDaoQueryDef::Close

После завершения использования объекта querydef, вызовите эту функцию-член.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

Закрытие querydef освобождает базового объекта DAO, но не уничтожает сохраненных объектов DAO querydef или C++ `CDaoQueryDef` объекта. Это не так же, как [CDaoDatabase::DeleteQueryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), которая удаляет querydef из querydefs-коллекция базы данных в DAO (если не временный querydef).

##  <a name="create"></a>  CDaoQueryDef::Create

Вызовите для создания нового сохраненного запроса или запроса временный эта функция-член.

```
virtual void Create(
    LPCTSTR lpszName = NULL,
    LPCTSTR lpszSQL = NULL);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Уникальное имя запроса, сохраненного в базе данных. Дополнительные сведения о строке см. в разделе «CreateQueryDef Method» в справке DAO. Если принять значение по умолчанию — пустая строка, создается временный querydef. Такой запрос не сохраняется в querydefs-коллекция.

*lpszSQL*<br/>
Строка SQL, определяющую запрос. Если вы принимаете значение NULL по умолчанию, позднее необходимо вызвать [SetSQL](#setsql) задать строку. А пока запрос не определено. Тем не менее, можно использовать неопределенный запрос для открытия набора записей; Дополнительные сведения см. примечания. Инструкции SQL должен быть определен перед добавлением querydef querydefs-коллекция.

### <a name="remarks"></a>Примечания

Если передать имя в *lpszName*, затем можно вызвать [Append](#append) для сохранения querydef в querydefs-коллекция базы данных. В противном случае объект временный querydef и не сохраняется. В любом случае querydef находится в открытом состоянии, и его можно использовать либо для создания [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта или вызвать querydef [Execute](#execute) функция-член.

Если не указать инструкцию SQL в *lpszSQL*, не может выполнить запрос с `Execute` , но его можно использовать для создания набора записей. В этом случае MFC использует инструкции SQL набора записей по умолчанию.

##  <a name="execute"></a>  CDaoQueryDef::Execute

Вызовите для выполнения запроса, определенного объектом querydef эта функция-член.

```
virtual void Execute(int nOptions = dbFailOnError);
```

### <a name="parameters"></a>Параметры

*nOptions*<br/>
Целое число, определяющее характеристики запроса. Дополнительные сведения см. в разделе «Выполнить метод» в справке DAO. Можно использовать оператор побитового или ( **&#124;**) для объединения следующие константы для этого аргумента:

- `dbDenyWrite` Запрет разрешения на запись к другим пользователям.

- `dbInconsistent` Несогласованных обновлений.

- `dbConsistent` Согласованное обновление системы.

- `dbSQLPassThrough` К серверу SQL. Вызывает инструкцию SQL для передачи в базу данных ODBC для обработки.

- `dbFailOnError` Значение по умолчанию. Откат обновления при возникновении ошибки и ошибки отчета пользователю.

- `dbSeeChanges` Если другой пользователь изменяет данные, которые вы изменяете, вызывают ошибку времени выполнения.

> [!NOTE]
>  Пояснение терминов «несогласованные» и «согласованный», см. в разделе «Выполнить метод» в справке DAO.

### <a name="remarks"></a>Примечания

Объекты QueryDef, используемые для выполнения, таким образом может представлять только одно из следующих типов запросов:

- Запросы

- Запросы к серверу

`Execute` не работает для запросов, возвращающих записей, включая запросы select. `Execute` обычно используется для массовой операции запросов, таких как **обновление**, **вставить**, или **SELECT INTO**, или для операций языка DDL для определения данных.

> [!TIP]
>  Предпочтительный способ работы с источниками данных ODBC — присоединение таблиц для Microsoft Jet (. База данных MDB). Дополнительные сведения см. в разделе «Доступ к внешней базы данных с DAO», в справке DAO.

Вызовите [GetRecordsAffected](#getrecordsaffected) функция-член объекта querydef, чтобы определить количество записей, затронутых последней `Execute` вызова. Например `GetRecordsAffected` возвращает сведения о количестве записей удаления, обновления или вставки при выполнении запроса. Число, возвращаемое не будет отражать изменения в связанных таблицах, когда cascade, обновляет или удаляет вступают в силу.

Если вы `dbInconsistent` и `dbConsistent` или если ни один, результатом является значение по умолчанию, `dbInconsistent`.

`Execute` Возвращает набор записей. С помощью `Execute` на запрос, который выбирает записи вызывает MFC для создания исключения типа [CDaoException](../../mfc/reference/cdaoexception-class.md).

##  <a name="getconnect"></a>  CDaoQueryDef::GetConnect

Вызов для получения строки подключения, связанный с источником данных querydef эта функция-член.

```
CString GetConnect();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [CString](../../atl-mfc-shared/reference/cstringt-class.md) содержит строку подключения для querydef.

### <a name="remarks"></a>Примечания

Эта функция используется только с источниками данных ODBC и некоторых драйверов. Он не используется с Microsoft Jet (. Баз данных MDB); в этом случае `GetConnect` возвращает пустую строку. Дополнительные сведения см. в разделе [SetConnect](#setconnect).

> [!TIP]
>  Предпочтительный способ работать с таблицами ODBC — подключите их к. База данных MDB. Дополнительные сведения см. в разделе «Доступ к внешней базы данных с DAO», в справке DAO.

Сведения о строках подключения см. в разделе «Свойства подключения», в справке DAO.

##  <a name="getdatecreated"></a>  CDaoQueryDef::GetDateCreated

Вызывайте эту функцию члена, чтобы получить дату создания объекта querydef.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, содержащий дату и время создания querydef.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.

##  <a name="getdatelastupdated"></a>  CDaoQueryDef::GetDateLastUpdated

Вызов, эта функция-член для получения объекта querydef дату последнего обновления, при каких-либо его свойств были изменены, например его имя, его строка SQL или его строку подключения.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) объект, содержащий дату и время последнего обновления querydef.

### <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.

##  <a name="getfieldcount"></a>  CDaoQueryDef::GetFieldCount

Вызовите эту функцию-член для получения числа полей в запросе.

```
short GetFieldCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число полей, определенных в запросе.

### <a name="remarks"></a>Примечания

`GetFieldCount` полезно для перебора всех полей в querydef. Для этой цели используйте `GetFieldCount` в сочетании с [GetFieldInfo](#getfieldinfo).

##  <a name="getfieldinfo"></a>  CDaoQueryDef::GetFieldInfo

Вызов для получения различного рода сведения о поле, определенное в querydef эта функция-член.

```
void GetFieldInfo(
    int nIndex,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetFieldInfo(
    LPCTSTR lpszName,
    CDaoFieldInfo& fieldinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Отсчитываемый от нуля индекс нужное поле в коллекции полей querydef, для поиска по индексу.

*FieldInfo*<br/>
Ссылку на `CDaoFieldInfo` объект, который возвращает запрошенные данные.

*dwInfoOptions*<br/>
Параметры, укажите, какие сведения о поле для извлечения. А также как они вызвать функцию возврата здесь перечислены доступные параметры:

- Размер имени, типа AFX_DAO_PRIMARY_INFO (по умолчанию), атрибуты

- AFX_DAO_SECONDARY_INFO сведения об основном плюс: Порядковый номер позиции необходимости разрешить нулевой длины, исходное поле, имя внешнего, исходной таблицы, порядок сортировки

- AFX_DAO_ALL_INFO первичного и вторичного сведения плюс: По умолчанию значение, текст проверки, правила проверки

*lpszName*<br/>
Строка, содержащая имя нужное поле, для поиска по имени. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Примечания

Описание сведений, возвращаемых в *fieldinfo*, см. в разделе [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют описательные сведения в разделе *dwInfoOptions* выше. Если вы запрашивали один уровень данных, вы получаете все предыдущие уровни подобных сведений.

##  <a name="getname"></a>  CDaoQueryDef::GetName

Вызовите эту функцию-член для извлечения имени запрос, представленный querydef.

```
CString GetName();
```

### <a name="return-value"></a>Возвращаемое значение

Имя запроса.

### <a name="remarks"></a>Примечания

QueryDef имена, уникальные имена, определяемые пользователем. Дополнительные сведения об именах querydef см. в разделе «Имя свойства» в справке DAO.

##  <a name="getodbctimeout"></a>  CDaoQueryDef::GetODBCTimeout

Вызовите эту функцию-член для извлечения выделенное время до истечения времени ожидания запроса к источнику данных ODBC.

```
short GetODBCTimeout();
```

### <a name="return-value"></a>Возвращаемое значение

Количество секунд, прежде чем запрос времени ожидания.

### <a name="remarks"></a>Примечания

Сведения о этого ограничения см. в разделе «Время ожидания ODBC свойство» в справке DAO.

> [!TIP]
>  Предпочтительный способ работы с таблицами ODBC является подключите их к Microsoft Jet (. База данных MDB). Дополнительные сведения см. в разделе «Доступ к внешней базы данных с DAO», в справке DAO.

##  <a name="getparametercount"></a>  CDaoQueryDef::GetParameterCount

Вызовите эту функцию-член для получения числа параметров в сохраненный запрос.

```
short GetParameterCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число параметров, определенных в запросе.

### <a name="remarks"></a>Примечания

`GetParameterCount` полезно для перебора всех параметров в querydef. Для этой цели используйте `GetParameterCount` в сочетании с [GetParameterInfo](#getparameterinfo).

Дополнительные сведения см. в разделах «Параметр объекта», «Коллекции параметров» и «параметры объявления (SQL)» в справке DAO.

##  <a name="getparameterinfo"></a>  CDaoQueryDef::GetParameterInfo

Вызов для получения сведений о параметра, определенного в querydef эта функция-член.

```
void GetParameterInfo(
    int nIndex,
    CDaoParameterInfo& paraminfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetParameterInfo(
    LPCTSTR lpszName,
    CDaoParameterInfo& paraminfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Параметры

*nIndex*<br/>
Отсчитываемый от нуля индекс нужный параметр в коллекцию Parameters querydef, для поиска по индексу.

*paraminfo*<br/>
Ссылку на [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) объект, который возвращает запрошенные данные.

*dwInfoOptions*<br/>
Параметры, укажите, какие сведения о параметре для извлечения. Доступен параметр приведена здесь, а также что он вызывает функцию возврата:

- Имя AFX_DAO_PRIMARY_INFO (по умолчанию), тип

*lpszName*<br/>
Строка, содержащая имя требуемого параметра, для поиска по имени. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Примечания

Описание сведений, возвращаемых в *paraminfo*, см. в разделе [CDaoParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют описательные сведения в разделе *dwInfoOptions* выше.

Дополнительные сведения см. в разделе «Параметры объявления (SQL)» в справке DAO.

##  <a name="getparamvalue"></a>  CDaoQueryDef::GetParamValue

Вызовите эту функцию-член для извлечения текущее значение указанного параметра, сохраненного в коллекции параметров querydef.

```
virtual COleVariant GetParamValue(LPCTSTR lpszName);
virtual COleVariant GetParamValue(int nIndex);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Имя параметра, значение которого требуется, для поиска по имени.

*nIndex*<br/>
Отсчитываемый от нуля индекс параметра в коллекции параметров querydef, для поиска по индексу. Можно получить это значение с вызовами [GetParameterCount](#getparametercount) и [GetParameterInfo](#getparameterinfo).

### <a name="return-value"></a>Возвращаемое значение

Объект класса [COleVariant](../../mfc/reference/colevariant-class.md) , содержащий значение параметра.

### <a name="remarks"></a>Примечания

Параметр доступны по имени или по ее порядковому номеру в коллекции.

Дополнительные сведения см. в разделе «Параметры объявления (SQL)» в справке DAO.

##  <a name="getrecordsaffected"></a>  CDaoQueryDef::GetRecordsAffected

Вызывайте эту функцию члена, чтобы определить, сколько записей были затронуты последнем вызове [Execute](#execute).

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Возвращаемое значение

Количество обработанных записей.

### <a name="remarks"></a>Примечания

Число, возвращаемое не будет отражать изменения в связанных таблицах, когда cascade, обновляет или удаляет вступают в силу.

Дополнительные сведения см. в разделе «RecordsAffected свойство» в справке DAO.

##  <a name="getreturnsrecords"></a>  CDaoQueryDef::GetReturnsRecords

Вызывайте эту функцию члена, чтобы определить, основано ли querydef на запрос, возвращающий записей.

```
BOOL GetReturnsRecords();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если querydef основан на запросе, который возвращает записи; в противном случае 0.

### <a name="remarks"></a>Примечания

Эта функция-член используется только для запросов к серверу. Дополнительные сведения о запросах SQL см. в разделе [Execute](#execute) функция-член. Дополнительные сведения о работе с запросами к серверу SQL, см. в разделе [SetReturnsRecords](#setreturnsrecords) функция-член.

Дополнительные сведения см. в разделе «ReturnsRecords свойство» в справке DAO.

##  <a name="getsql"></a>  CDaoQueryDef::GetSQL

Вызовите эту функцию-член для получения инструкции SQL, определяющей запрос, на котором основан querydef.

```
CString GetSQL();
```

### <a name="return-value"></a>Возвращаемое значение

Инструкция SQL, определяющей запрос, на котором основан querydef.

### <a name="remarks"></a>Примечания

Затем будет, скорее всего, проанализировать строку для ключевых слов, имена таблиц и т. д.

Дополнительные сведения см в разделах «Свойства SQL», «Сравнение Microsoft Jet базы данных ядра SQL и ANSI SQL» и «Запрос базы данных с помощью SQL в код» в справке DAO.

##  <a name="gettype"></a>  CDaoQueryDef::GetType

Вызовите для определения типа запроса querydef эта функция-член.

```
short GetType();
```

### <a name="return-value"></a>Возвращаемое значение

Тип запроса, определенного с querydef. Значения см. в разделе "Примечания".

### <a name="remarks"></a>Примечания

Тип запроса задается то, что указано в строке SQL querydef при создании querydef или вызывать существующие querydef [SetSQL](#setsql) функция-член. Тип запроса возвращает эта функция может принимать одно из следующих значений:

- `dbQSelect` Выберите

- Действие `dbQAction`

- `dbQCrosstab` Перекрестный

- `dbQDelete` Удаление

- `dbQUpdate` Обновление

- `dbQAppend` добавить

- `dbQMakeTable` Создание таблицы

- `dbQDDL` Определение данных

- `dbQSQLPassThrough` К серверу

- `dbQSetOperation` Объединение

- `dbQSPTBulk` Используется с `dbQSQLPassThrough` , чтобы определить запрос, который не возвращает записей.

> [!NOTE]
>  Чтобы создать запрос к серверу SQL, не устанавливайте `dbSQLPassThrough` константы. Это задается автоматически ядром СУБД Microsoft Jet при создании объекта querydef и задайте строку подключения.

Сведения о строках SQL см. в разделе [GetSQL](#getsql). Сведения о типах запросов см. в разделе [Execute](#execute).

##  <a name="isopen"></a>  CDaoQueryDef::IsOpen

Вызывайте эту функцию члена, чтобы определить, является ли `CDaoQueryDef` объекта в данный момент открыт.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение `CDaoQueryDef` объект сейчас открыт; в противном случае — 0.

### <a name="remarks"></a>Примечания

Прежде чем использовать его для вызова querydef должно быть в открытом состоянии [Execute](#execute) или для создания [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта. Расшифровка querydef в открытом состоянии вызове либо [создать](#create) (для нового querydef) или [откройте](#open) (для существующего querydef).

##  <a name="m_pdatabase"></a>  CDaoQueryDef::m_pDatabase

Содержит указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объект, связанный с объектом querydef.

### <a name="remarks"></a>Примечания

Используйте этот указатель, если требуется прямой доступ к базе данных — например, для получения ссылки на другие querydef или набора записей объектов в коллекции базы данных.

##  <a name="m_pdaoquerydef"></a>  CDaoQueryDef::m_pDAOQueryDef

Содержит указатель на интерфейс OLE для базового объекта querydef DAO.

### <a name="remarks"></a>Примечания

Этот указатель предоставляется на полноту и согласованность с другими классами. Тем не менее так как MFC полностью скорее инкапсулирует DAO querydefs, вы вряд ли он нужен. Если вы используете его, сделайте это осторожно — в частности, не изменяйте значение указателя, если не известно, что вы выполняете.

##  <a name="open"></a>  CDaoQueryDef::Open

Вызывайте эту функцию члена, чтобы открыть querydef, ранее сохраненных в базе данных querydefs-коллекция.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Строка, содержащая имя сохраненного querydef, чтобы открыть. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Примечания

Открыв querydef, можно вызвать его [Execute](#execute) функция-член или используйте querydef, чтобы создать [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта.

##  <a name="setconnect"></a>  CDaoQueryDef::SetConnect

Вызывайте эту функцию члена, чтобы задать строку подключения объекта querydef.

```
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Параметры

*lpszConnect*<br/>
Строка, содержащая строку подключения для связанного [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.

### <a name="remarks"></a>Примечания

Строка подключения используется для передачи дополнительных сведений к ODBC и некоторые драйверы ISAM, при необходимости. Он не используется для Microsoft Jet (. Баз данных MDB).

> [!TIP]
>  Предпочтительный способ работать с таблицами ODBC — подключите их к. База данных MDB.

Перед выполнением querydef, который представляет запрос к серверу SQL к источнику данных ODBC, задайте строку подключения с `SetConnect` и вызвать [SetReturnsRecords](#setreturnsrecords) для указания, является ли запрос возвращает записи.

Дополнительные сведения о структуре и примеры компоненты строки соединения в строке подключения см. в разделе «Свойства подключения», в справке DAO.

##  <a name="setname"></a>  CDaoQueryDef::SetName

Вызовите эту функцию-член, если вы хотите изменить имя querydef, который не является временным.

```
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Строка, содержащая новое имя для запроса nontemporary в связанном [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.

### <a name="remarks"></a>Примечания

QueryDef имена являются именами уникальный, определяемых пользователем. Вы можете вызвать `SetName` перед querydef объект добавляется к querydefs-коллекция.

##  <a name="setodbctimeout"></a>  CDaoQueryDef::SetODBCTimeout

Вызывайте эту функцию члена, чтобы задать предельное время до истечения времени ожидания запроса к источнику данных ODBC.

```
void SetODBCTimeout(short nODBCTimeout);
```

### <a name="parameters"></a>Параметры

*nODBCTimeout*<br/>
Количество секунд, прежде чем запрос времени ожидания.

### <a name="remarks"></a>Примечания

Эта функция-член позволяет переопределить значение по умолчанию количество секунд перед выполнением последующих операций в подключенном источнике данных «время ожидания истекло». Операция может время ожидания выполнения из-за проблем доступа к сети, время обработки запроса чрезмерное и т. д. Вызовите `SetODBCTimeout` до выполнения запроса с этой querydef, если вы хотите изменить запрашиваемое значение времени ожидания. (Как ODBC используются подключения, значение времени ожидания является одинаковым для всех клиентов в то же соединение.)

Значение по умолчанию для времени ожидания запросов составляет 60 секунд.

##  <a name="setparamvalue"></a>  CDaoQueryDef::SetParamValue

Вызывайте эту функцию член, чтобы задать значение параметра в querydef во время выполнения.

```
virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Имя параметра, значение которого требуется задать.

*varValue*<br/>
Задаваемое значение; см. в разделе "Примечания".

*nIndex*<br/>
Порядковая позиция параметра в коллекции параметров querydef. Можно получить это значение с вызовами [GetParameterCount](#getparametercount) и [GetParameterInfo](#getparameterinfo).

### <a name="remarks"></a>Примечания

Параметр должна быть уже установлена как часть строки querydef SQL. Параметр доступны по имени или по ее порядковому номеру в коллекции.

Укажите значение, устанавливаемое как `COleVariant` объекта. Дополнительные сведения о настройке в нужное значение и введите ваш `COleVariant` объекта, см. в разделе класса [COleVariant](../../mfc/reference/colevariant-class.md).

##  <a name="setreturnsrecords"></a>  CDaoQueryDef::SetReturnsRecords

Вызовите эту функцию-член в рамках процесса настройки запроса к серверу внешней базе данных.

```
void SetReturnsRecords(BOOL bReturnsRecords);
```

### <a name="parameters"></a>Параметры

*bReturnsRecords*<br/>
Передается значение false, если запрос на внешней базы данных возвращает записи; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

В этом случае необходимо создать querydef и его свойства настраиваются в другом `CDaoQueryDef` функций-членов. Описание внешних баз данных, см. в разделе [SetConnect](#setconnect).

##  <a name="setsql"></a>  CDaoQueryDef::SetSQL

Вызывайте эту функцию члена, чтобы задать инструкцию SQL, которая выполняет querydef.

```
void SetSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>Параметры

*lpszSQL*<br/>
Строка, содержащая полную инструкцию SQL, подходящий для выполнения. Синтаксис этой строки зависит от СУБД, используемой для запроса. Описание синтаксиса, который используется в ядре СУБД Microsoft Jet см. в разделе «Построение инструкций в код SQL» в справке DAO.

### <a name="remarks"></a>Примечания

Типичное применение `SetSQL` является настройка объект querydef для использования в запросе к серверу SQL. (Синтаксис запросов к серверу на целевой СУБД, см. в документации по используемой СУБД.)

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)<br/>
[Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)<br/>
[Класс CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)<br/>
[Класс CDaoException](../../mfc/reference/cdaoexception-class.md)
