---
title: Класс CДао-КуириДеф
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
ms.openlocfilehash: ed298c40daa9485683d0b989e47b97fdce9f6562
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754709"
---
# <a name="cdaoquerydef-class"></a>Класс CДао-КуириДеф

Представляет определение запроса или QueryDef, как правило, сохраненный в базе данных.

## <a name="syntax"></a>Синтаксис

```
class CDaoQueryDef : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDao-КуириДеф::CDao-КуириДеф](#cdaoquerydef)|Формирует объект `CDaoQueryDef`. Следующий `Open` `Create`звонок или , в зависимости от ваших потребностей.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDao-КуириДеф::Приложение](#append)|Пригоз: запрос к сбору queryDefs базы данных в качестве сохраненного запроса.|
|[CDao-КуириДеф::CanUpdate](#canupdate)|Возвращает ненулевой, если запрос может обновить базу данных.|
|[CDao КуириДеф::Закрыть](#close)|Закрывает объект запроса. Уничтожьте объект СЗ, когда вы закончите с ним.|
|[CDao-КуириДеф::Создание](#create)|Создает базовый объект dAO querydef. Используйте запрос в качестве временного запроса `Append` или вызывайте его в базе данных.|
|[CDao-КуириДеф::Выполнение](#execute)|Выполняет запрос, определяемый объектом запроса.|
|[CDao-КуириДеф::GetConnect](#getconnect)|Возвращает строку соединения, связанную с запросом. Строка соединения определяет источник данных. (Только для сквозных запросов S'L; в противном случае пустая строка.)|
|[CDao-КуириДеф::GetDateCreated](#getdatecreated)|Возвращает дату создания сохраненного запроса.|
|[CDao-КуириДеф::GetDateLastUpdated](#getdatelastupdated)|Возвращает дату последнего обновления сохраненного запроса.|
|[CDao-КуириДеф::GetFieldCount](#getfieldcount)|Возвращает количество полей, определяемых запросом.|
|[CDao КуириДеф::GetFieldInfo](#getfieldinfo)|Возвращает информацию об определенном поле, определенном в запросе.|
|[CDao-КуириДеф::GetName](#getname)|Возвращает имя запроса.|
|[CDao-КуэриДеф::GetODBCTimeout](#getodbctimeout)|Возвращает значение тайм-аута, используемое ODBC (для запроса ODBC) при выполнении запроса. Это определяет, как долго можно выполнить действие запроса.|
|[CDao-КуириДеф::GetParameterCount](#getparametercount)|Возвращает количество параметров, определенных для запроса.|
|[CDao-КуириДеф::GetParameterInfo](#getparameterinfo)|Возвращает информацию об определенном параметре в запрос.|
|[CDao-КуириДеф::GetParamValue](#getparamvalue)|Возвращает значение заданного параметра в запрос.|
|[CDao-КуириДеф::GetRecordsAffected](#getrecordsaffected)|Возвращает количество записей, затронутых запросом действия.|
|[CDao-КуириДеф::GetReturnsRecords](#getreturnsrecords)|Возвращает ненулевой, если запрос, определяемый запросом, возвращает записи.|
|[CDao-КуириДеф::GetS'L](#getsql)|Возвращает строку S'L, определяющую запрос, определяемый запросом.|
|[CDao-КуириДеф::GetType](#gettype)|Возвращает тип запроса: удалите, обновите, придаток, стол и так далее.|
|[CDao-КуириДеф::IsOpen](#isopen)|Возвращает ненулевой, если запрос открыт и может быть выполнен.|
|[CDao КуириДеф::Открыто](#open)|Открывает существующий запрос, хранящийся в коллекции queryDefs базы данных.|
|[CDao-КуириДеф::SetConnect](#setconnect)|Устанавливает строку соединения для сквозного запроса s'L на источнике данных ODBC.|
|[CDao-КуириДеф::SetName](#setname)|Устанавливает имя сохраненного запроса, заменяя имя, используемеее при создании запроса.|
|[CDao-КуэриДеф::SetODBCTimeout](#setodbctimeout)|Устанавливает значение тайм-аута, используемое ODBC (для запроса ODBC) при выполнении запроса.|
|[CDao-КуириДеф::SetParamValue](#setparamvalue)|Устанавливает значение заданного параметра в запросе.|
|[CDao-КуириДеф::SetReturnsRecords](#setreturnsrecords)|Определяет, возвращает ли запрос записи. Установка этого атрибута на TRUE действительна только для сквозных запросов S'L.|
|[CDao-КуириДеф::SetS'L](#setsql)|Устанавливает строку S'L, определяющую запрос, определяемый запросом.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDao-КевириДеф::m_pDAOQueryDef](#m_pdaoquerydef)|Указатель на интерфейс OLE для базового объекта querydef DAO.|
|[CDao-КуириДеф::m_pDatabase](#m_pdatabase)|Указатель на `CDaoDatabase` объект, с которым связан запрос. Запрос может быть сохранен в базе данных или нет.|

## <a name="remarks"></a>Remarks

Запрос — это объект доступа к данным, содержащий оператора S'L, описывающий запрос, и его свойства, такие как «Дата создана» и «Тайм-аут ODBC». Вы также можете создавать временные объекты запроса, не сохраняя их, но это удобно - и гораздо более эффективно - для сохранения обычно повторно используемых запросов в базе данных. Объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) поддерживает коллекцию под названием «Коллекция queryDefs», которая содержит сохраненные запросы.

> [!NOTE]
> Классы баз данных DAO отличаются от классов баз данных MFC на основе open Database Connectivity (ODBC). Все названия классов баз данных DAO имеют префикс "CDao". Вы все еще можете получить доступ к источникам данных ODBC с классами DAO. В целом, классы МФЦ на основе DAO более способны, чем классы МФЦ на основе ODBC; классы на базе DAO могут получать доступ к данным, в том числе через драйверы ODBC, через свой собственный движок баз данных. Классы, основанные на DAO, также поддерживают операции языка определения данных (DDL), такие как добавление таблиц через классы, без прямого вызова DAO.

## <a name="usage"></a>Использование

Используйте объекты запроса либо для работы с существующим сохраненным запросом, либо для создания нового сохраненного запроса или временного запроса:

1. Во всех случаях сначала `CDaoQueryDef` постройте объект, поставив указатель на объект [CDaoDatabase,](../../mfc/reference/cdaodatabase-class.md) к которому принадлежит запрос.

1. Затем сделайте следующее, в зависимости от того, что вы хотите:

   - Чтобы использовать существующий сохраненный запрос, позвоните в функцию [«Открытая](#open) функция пользователя объекта запроса», предоставив имя сохраненного запроса.

   - Чтобы создать новый сохраненный запрос, позвоните в функцию [создания](#create) объекта запроса, предоставив имя запроса. Затем позвоните [в Append,](#append) чтобы сохранить запрос, приложив его к коллекции queryDefs базы данных. `Create`помещает запрос в открытое состояние, поэтому `Create` после звонка `Open`не звоните.

   - Чтобы создать временный запрос, `Create`позвоните . Передайте пустую строку для имени запроса. Не вызывайте `Append`.

Когда вы закончите использовать объект querydef, позвоните в функцию участника [Close;](#close) затем уничтожить объект querydef.

> [!TIP]
> Самый простой способ создания сохраненных запросов — создать их и хранить их в базе данных с помощью Microsoft Access. Затем вы можете открыть и использовать их в своем коде MFC.

## <a name="purposes"></a>Целей

Объект запроса можно использовать для любой из следующих целей:

- Создание `CDaoRecordset` объекта

- Вызов функции элемента `Execute` объекта для непосредственного выполнения запроса действия или сквозного запроса S'L

Объект запроса можно использовать для любого типа запроса, включая выбор, действие, перекрестный удар, удаление, обновление, приложение, сделать-таблицу, определение данных, сквозный s-L, союз и массовые запросы. Тип запроса определяется содержанием оператора S'L, которое вы поставляете. Для получения информации `Execute` о типах запросов см. [GetType](#gettype) Записи обычно используются для возврата строк запросов, как правило, те, которые используют **SELECT ... Из** ключевых слов. `Execute`чаще всего используется для оптовых операций. Для получения дополнительной информации, [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)см. [Execute](#execute)

## <a name="querydefs-and-recordsets"></a>Керидефы и записи

Для использования объекта querydef `CDaoRecordset` для создания объекта обычно создается или открывается querydef, как описано выше. Затем создайте объект регистрации, передав указатель объекту querydef при вызове [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Запрос, который вы проходите, должен находиться в открытом состоянии. Для получения дополнительной информации, см класс [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Вы не можете использовать запрос для создания набора записей (наиболее распространенное использование для querydef), если он находится в открытом состоянии. Поместите querydef в открытое `Open` состояние, позвонив либо `Create`или .

## <a name="external-databases"></a>Внешние базы данных

Объекты querydef являются предпочтительным способом использования родного диалекта S'L внешнего движка базы данных. Например, можно создать запрос «Переакт СЗЛ» (как используется на сервере Microsoft S'L) и хранить его в объекте запроса. При необходимости использования запроса S'L, не основанного на движке базы данных Microsoft Jet, необходимо предоставить строку соединения, уотягоцу на внешний источник данных. Запросы с действительными строками соединения обходят движок базы данных и передают запрос непосредственно на сервер внешней базы данных для обработки.

> [!TIP]
> Предпочтительным способом работы со таблицами ODBC является их присоединение к Microsoft Jet (. MDB) базы данных.

Для получения соответствующей информации в DDK можно ознакомиться на темах "Объект queryDef", "Коллекция квидефоров" и "Объект CdbDatabase".

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDaoQueryDef`

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="cdaoquerydefappend"></a><a name="append"></a>CDao-КуириДеф::Приложение

Вызов исчерпать эту функцию участника после вызова [Создать](#create) для создания нового объекта querydef.

```
virtual void Append();
```

### <a name="remarks"></a>Remarks

`Append`сохраняет запрос в базе данных, приговывая объект к сбору queryDefs базы данных. Вы можете использовать запрос в качестве временного объекта без добавления, но если `Append`вы хотите, чтобы он сохранился, вы должны позвонить в .

При попытке придатка временного объекта запроса MFC бросает исключение типа [CDaoException.](../../mfc/reference/cdaoexception-class.md)

## <a name="cdaoquerydefcanupdate"></a><a name="canupdate"></a>CDao-КуириДеф::CanUpdate

Вызовите эту функцию участника, чтобы определить, можно ли изменить запрос, например, изменить его имя или строку S'L.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если вам разрешено изменять запрос; в противном случае 0.

### <a name="remarks"></a>Remarks

Вы можете изменить запрос, если:

- Он не основан на базе данных, которая открыта только для чтения.

- У вас есть разрешения на обновление базы данных.

   Это зависит от того, реализованы ли вы функции безопасности. МФЦ не обеспечивает поддержку безопасности; Вы должны реализовать его самостоятельно, позвонив в DAO напрямую или используя Microsoft Access. Смотрите тему "Разрешения собственности" в DAO Помощь.

## <a name="cdaoquerydefcdaoquerydef"></a><a name="cdaoquerydef"></a>CDao-КуириДеф::CDao-КуириДеф

Формирует объект `CDaoQueryDef`.

```
CDaoQueryDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Параметры

*pDatabase*<br/>
Указатель на открытый объект [CDaoDatabase.](../../mfc/reference/cdaodatabase-class.md)

### <a name="remarks"></a>Remarks

Объект может представлять существующий запрос, хранящийся в коллекции queryDefs базы данных, новый запрос, который будет храниться в коллекции, или временный запрос, который не будет храниться. Ваш следующий шаг зависит от типа запроса:

- Если объект представляет существующий запрос, позвоните в функцию [«Открытая](#open) функция объекта», чтобы инициализировать его.

- Если объект представляет собой новый запрос для сохранения, вызов исчерг функцию [члена объекта Create.](#create) Это добавляет объект в коллекцию queryDefs базы данных. Затем `CDaoQueryDef` вызов функций участника для установки атрибутов объекта. Наконец, позвоните [В аппенд](#append).

- Если объект представляет собой временный запрос (не должен сохраняться в базе данных), вызов, `Create`передающий пустую строку для имени запроса. После `Create`вызова инициализируем запрос, непосредственно установив его атрибуты. Не вызывайте `Append`.

Чтобы установить атрибуты запроса, можно использовать функции участника [SetName,](#setname) [SetS'L,](#setsql) [SetConnect,](#setconnect) [SetODBCTimeout](#setodbctimeout)и функции участника [SetReturnsRecords.](#setreturnsrecords)

Когда вы закончите с объектом querydef, позвоните в функцию [«Закрыть».](#close) Если у вас есть указатель на запрос, используйте оператора **удаления,** чтобы уничтожить объект C'.

## <a name="cdaoquerydefclose"></a><a name="close"></a>CDao КуириДеф::Закрыть

Вызовите эту функцию участника, когда вы закончите с помощью объекта querydef.

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

Закрытие запроса выпускает базовый объект DAO, но не уничтожает сохраненный объект `CDaoQueryDef` querydef DAO или объект C'. Это не то же самое, [что CDaoDatabase: :Delete'e'eryDef](../../mfc/reference/cdaodatabase-class.md#deletequerydef), который удаляет запрос из коллекции queryDefs базы данных в DAO (если не временный запрос).

## <a name="cdaoquerydefcreate"></a><a name="create"></a>CDao-КуириДеф::Создание

Вызовите эту функцию участника для создания нового сохраненного запроса или нового временного запроса.

```
virtual void Create(
    LPCTSTR lpszName = NULL,
    LPCTSTR lpszSQL = NULL);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Уникальное название запроса сохранено в базе данных. Подробнее о строке читайте в справке DAO.ru по теме «Метод создания «Создать» в DAO. Если вы принимаете значение по умолчанию, создается пустая строка, создается временный запрос. Такой запрос не сохраняется в коллекции queryDefs.

*lpszS'L*<br/>
Строка S'L, определяющая запрос. Если вы принимаете значение NULL по умолчанию, необходимо позже вызвать [SetS'L,](#setsql) чтобы установить строку. До тех пор запрос не определен. Однако можно использовать неопределенный запрос для открытия набора записей; подробнее о ней. Заявление s'L должно быть определено, прежде чем вы сможете придать запрос коллекции queryDefs.

### <a name="remarks"></a>Remarks

Если вы передаете имя в *lpszName,* вы можете вызвать [приложение,](#append) чтобы сохранить querydef в коллекции queryDefs базы данных. В противном случае объект является временным запросом и не сохраняется. В любом случае запрос находится в открытом состоянии, и его можно использовать для создания объекта [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) или вызвать функцию [члена-участника](#execute) querydef.

Если вы не предоставите выписку по S'L в *lpszS'L,* вы не можете запустить запрос, `Execute` но вы можете использовать его для создания набора записей. В этом случае MFC использует заявление рекорда по умолчанию.

## <a name="cdaoquerydefexecute"></a><a name="execute"></a>CDao-КуириДеф::Выполнение

Вызовите эту функцию участника для выполнения запроса, определяемого объектом запроса.

```
virtual void Execute(int nOptions = dbFailOnError);
```

### <a name="parameters"></a>Параметры

*nВарианты*<br/>
Цель, определяющая характеристики запроса. Для получения соответствующей информации смотрите тему "Выполнить метод" в Справке DAO. Вы можете использовать оператора bitwise-OR **(&#124;) **для объединения следующих констант для этого аргумента:

- `dbDenyWrite`Запретить писать разрешение другим пользователям.

- `dbInconsistent`Несовместимые обновления.

- `dbConsistent`Последовательные обновления.

- `dbSQLPassThrough`Проходной проход. Вызывает передаваемый в базу данных ODBC для обработки оператора S'L.

- `dbFailOnError`Значение по умолчанию. Откат обновлений в случае ошибки и сообщите об ошибке пользователю.

- `dbSeeChanges`Создайте ошибку времени выполнения, если другой пользователь изменяет данные, которые вы редактируете.

> [!NOTE]
> Для объяснения терминов "непоследовательный" и "последовательный", см. тему "Выполнить метод" в DAO Помощь.

### <a name="remarks"></a>Remarks

Объекты querydef, используемые для выполнения таким образом, могут представлять только один из следующих типов запросов:

- Запросы действий

- Сквозные запросы

`Execute`не работает для запросов, возвращающие записи, такие как выберите запросы. `Execute`обычно используется для массовых запросов операции, таких как **UPDATE,** **INSERT**, или **SELECT INTO**, или для языка определения данных (DDL) операций.

> [!TIP]
> Предпочтительным способом работы с источниками данных ODBC является присоединение таблиц к Microsoft Jet (. MDB) базы данных. Для получения дополнительной информации смотрите тему "Доступ к внешним базам данных с DAO" в Справке DAO.

Позвоните функции участника [GetRecordsAffected](#getrecordsaffected) объекта запроса, чтобы определить количество `Execute` записей, затронутых последним вызовом. Например, `GetRecordsAffected` возвращает информацию о количестве удаленных, обновленных или вставленных записей при выполнения запроса действий. Обратный счет не будет отражать изменения в смежных таблицах, когда каскад обновляется или удаляет в силе.

Если вы `dbInconsistent` включаете оба и `dbConsistent` или если вы `dbInconsistent`не включаете ни один, результатом является по умолчанию, .

`Execute`не возвращает рекорд. Использование `Execute` запроса, который выбирает записи, заставляет MFC выбросить исключение типа [CDaoException.](../../mfc/reference/cdaoexception-class.md)

## <a name="cdaoquerydefgetconnect"></a><a name="getconnect"></a>CDao-КуириДеф::GetConnect

Вызовите эту функцию участника, чтобы получить строку соединения, связанную с источником данных querydef.

```
CString GetConnect();
```

### <a name="return-value"></a>Возвращаемое значение

[CString,](../../atl-mfc-shared/reference/cstringt-class.md) содержащий строку соединения для querydef.

### <a name="remarks"></a>Remarks

Эта функция используется только с источниками данных ODBC и некоторыми драйверами ISAM. Он не используется с Microsoft Jet (. MDB) базы данных; в этом `GetConnect` случае возвращаетпустую строку. Для получения дополнительной информации [см.](#setconnect)

> [!TIP]
> Предпочтительный способ работы со таблицами ODBC заключается в том, чтобы прикрепить их к . База данных MDB. Для получения дополнительной информации смотрите тему "Доступ к внешним базам данных с DAO" в Справке DAO.

Для получения информации о строках подключения см.

## <a name="cdaoquerydefgetdatecreated"></a><a name="getdatecreated"></a>CDao-КуириДеф::GetDateCreated

Вызовите эту функцию участника, чтобы получить дату создания объекта запроса.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) содержащий дату и время создания запроса.

### <a name="remarks"></a>Remarks

Для получения соответствующей информации, см.

## <a name="cdaoquerydefgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDao-КуириДеф::GetDateLastUpdated

Вызовите эту функцию участника, чтобы получить дату последнего обновления объекта запроса — когда любое из его свойств было изменено, например, его имя, строка S'L или строка соединения.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime,](../../atl-mfc-shared/reference/coledatetime-class.md) содержащий дату и время последнего обновления запроса.

### <a name="remarks"></a>Remarks

Для получения соответствующей информации, см.

## <a name="cdaoquerydefgetfieldcount"></a><a name="getfieldcount"></a>CDao-КуириДеф::GetFieldCount

Вызов исчисляйте эту функцию участника, чтобы получить количество полей в запросе.

```
short GetFieldCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество полей, определенных в запросе.

### <a name="remarks"></a>Remarks

`GetFieldCount`полезно для циклирования всех полей в запросе. Для этой цели, использование `GetFieldCount` в сочетании с [GetFieldInfo](#getfieldinfo).

## <a name="cdaoquerydefgetfieldinfo"></a><a name="getfieldinfo"></a>CDao КуириДеф::GetFieldInfo

Вызовите эту функцию участника для получения различного рода информации о поле, определенном в querydef.

```cpp
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

*Nindex*<br/>
Индекс нулевой основе желаемого поля в коллекции полей querydef для поиска по индексу.

*Fieldinfo*<br/>
Ссылка на `CDaoFieldInfo` объект, возвращаюа информацию, запрашиваемую.

*dwInfoOptions*<br/>
Параметры, которые определяют, какую информацию о поле для извлечения. Доступные варианты перечислены здесь вместе с тем, что они вызывают функцию возвращения:

- AFX_DAO_PRIMARY_INFO (по умолчанию) Имя, тип, размер, атрибуты

- AFX_DAO_SECONDARY_INFO Первичная информация плюс: Порядкиная позиция, Требуется, Разрешить нулевую длину, Исходное поле, Иностранное имя, Таблица Источников, Сопоставление порядка

- AFX_DAO_ALL_INFO Первичная и второстепенная информация плюс: Значение по умолчанию, Текст валидации, Правило валидации

*lpszName*<br/>
Строка, содержащая имя нужного поля, для поиска по имени. Вы можете использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Remarks

Для описания информации, возвращенной в [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) *fieldinfo*, см. Эта структура имеет членов, которые соответствуют описательной информации в *соответствии с dwInfoOptions* выше. Если вы запрашиваете один уровень информации, вы получите любые предыдущие уровни информации, а также.

## <a name="cdaoquerydefgetname"></a><a name="getname"></a>CDao-КуириДеф::GetName

Вызовите эту функцию пользователя, чтобы получить имя запроса, представленного запросом.

```
CString GetName();
```

### <a name="return-value"></a>Возвращаемое значение

Имя запроса.

### <a name="remarks"></a>Remarks

Имена querydef — это уникальные имена, определяемые пользователем. Для получения дополнительной информации об именах запросов смотрите тему "Название собственности" в справке DAO.

## <a name="cdaoquerydefgetodbctimeout"></a><a name="getodbctimeout"></a>CDao-КуэриДеф::GetODBCTimeout

Вызов этой функции участника для извлечения текущего ограничения по времени до того, как запрос к исходу источника данных ODBC будет выходить из-под заседать.

```
short GetODBCTimeout();
```

### <a name="return-value"></a>Возвращаемое значение

Время ожидания запроса (в секундах).

### <a name="remarks"></a>Remarks

Подробнее об этом ограничении по времени читайте в теме "Недвижимость ODBCTimeout" в справке DAO.

> [!TIP]
> Предпочтительным способом работы со таблицами ODBC является их присоединение к Microsoft Jet (. MDB) базы данных. Для получения дополнительной информации смотрите тему "Доступ к внешним базам данных с DAO" в Справке DAO.

## <a name="cdaoquerydefgetparametercount"></a><a name="getparametercount"></a>CDao-КуириДеф::GetParameterCount

Вызов исчисляйте эту функцию участника, чтобы получить количество параметров в сохраненном запросе.

```
short GetParameterCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество параметров, определенных в запросе.

### <a name="remarks"></a>Remarks

`GetParameterCount`полезно для циклирования всех параметров в запросе. Для этой цели, использование `GetParameterCount` в сочетании с [GetParameterInfo](#getparameterinfo).

Для получения соответствующей информации в справке DAO можно ознакомиться на темах "Объект параметра", "Коллекция параметров" и "Декларация Паратеса" (СЗЛ)" в справке DAO.

## <a name="cdaoquerydefgetparameterinfo"></a><a name="getparameterinfo"></a>CDao-КуириДеф::GetParameterInfo

Позвоните этой функции участника, чтобы получить информацию о параметре, определенном в querydef.

```cpp
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

*Nindex*<br/>
Нулевой индекс желаемого параметра в коллекции параметров querydef для поиска по индексу.

*paraminfo*<br/>
Ссылка на объект [CDaoParameterInfo,](../../mfc/reference/cdaoparameterinfo-structure.md) который возвращает запрашиваемую информацию.

*dwInfoOptions*<br/>
Параметры, которые определяют, какую информацию о параметре для извлечения. Доступный вариант указан здесь вместе с тем, что он вызывает функцию возвращения:

- AFX_DAO_PRIMARY_INFO (по умолчанию) имя, тип

*lpszName*<br/>
Строка, содержащая имя желаемого параметра, для поиска по имени. Вы можете использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Remarks

Для описания информации, возвращенной в *paraminfo*, см. [CDao ParameterInfo](../../mfc/reference/cdaoparameterinfo-structure.md) структуры. Эта структура имеет членов, которые соответствуют описательной информации в *соответствии с dwInfoOptions* выше.

Для получения соответствующей информации, см.

## <a name="cdaoquerydefgetparamvalue"></a><a name="getparamvalue"></a>CDao-КуириДеф::GetParamValue

Вызовите эту функцию участника для получения текущего значения указанного параметра, хранящегося в коллекции параметров querydef.

```
virtual COleVariant GetParamValue(LPCTSTR lpszName);
virtual COleVariant GetParamValue(int nIndex);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Имя параметра, значение которого вы хотите, для поиска по имени.

*Nindex*<br/>
Нулевой индекс параметра в коллекции параметров querydef для поиска по индексу. Вы можете получить это значение с вызовами [getParameterCount](#getparametercount) и [GetParameterInfo](#getparameterinfo).

### <a name="return-value"></a>Возвращаемое значение

Объект класса [COleVariant,](../../mfc/reference/colevariant-class.md) содержащий значение параметра.

### <a name="remarks"></a>Remarks

Вы можете получить доступ к параметру либо по имени, либо по его ординаторному положению в коллекции.

Для получения соответствующей информации, см.

## <a name="cdaoquerydefgetrecordsaffected"></a><a name="getrecordsaffected"></a>CDao-КуириДеф::GetRecordsAffected

Вызовите эту функцию участника, чтобы определить, сколько записей было затронуто последним вызовом [Выполнения.](#execute)

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Возвращаемое значение

Количество обработанных записей.

### <a name="remarks"></a>Remarks

Обратный счет не будет отражать изменения в смежных таблицах, когда каскад обновляется или удаляет в силе.

Для соответствующей информации смотрите тему "RecordsAffected Собственности" в DAO Помощь.

## <a name="cdaoquerydefgetreturnsrecords"></a><a name="getreturnsrecords"></a>CDao-КуириДеф::GetReturnsRecords

Вызовите эту функцию участника, чтобы определить, основан ли запрос на основе запроса, возвращающего записи.

```
BOOL GetReturnsRecords();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если запрос основан на запросе, который возвращает записи; в противном случае 0.

### <a name="remarks"></a>Remarks

Эта функция члена используется только для сквозных запросов S'L. Для получения более подробной информации о запросах на S'L можно ознакомиться на функции участника [«Выполнения».](#execute) Для получения более подробной информации о работе [SetReturnsRecords](#setreturnsrecords) с сквозными запросами, см.

Для получения соответствующей информации, см.

## <a name="cdaoquerydefgetsql"></a><a name="getsql"></a>CDao-КуириДеф::GetS'L

Вызовите эту функцию участника, чтобы получить выписку s'L, определяющую запрос, на котором основан запрос.

```
CString GetSQL();
```

### <a name="return-value"></a>Возвращаемое значение

Выписка, определяющая запрос, на котором основан запрос.

### <a name="remarks"></a>Remarks

Затем, вероятно, вы разберете строку для ключевых слов, названий таблиц и так далее.

Для получения соответствующей информации в справке DAO(S'L Help) можно ознакомиться с темами: «Недвижимость S'L», «Сравнение двигателей баз данных Microsoft Jet Engine S'L и ANSI S'L» и «Представление базы данных с помощью S'L в коде».

## <a name="cdaoquerydefgettype"></a><a name="gettype"></a>CDao-КуириДеф::GetType

Вызовите эту функцию участника, чтобы определить тип запроса querydef.

```
short GetType();
```

### <a name="return-value"></a>Возвращаемое значение

Тип запроса, определяемый запросом. Для значений, см.

### <a name="remarks"></a>Remarks

Тип запроса устанавливается тем, что вы указываете в строке s'L запроса при создании запроса или вызове функции участника существующего запроса [SetS'L.](#setsql) Тип запроса, возвращенный этой функцией, может быть одним из следующих значений:

- `dbQSelect`Выберите

- Действие `dbQAction`

- `dbQCrosstab`Перекрестного

- `dbQDelete`Удалить

- `dbQUpdate` Update

- `dbQAppend`Добавить

- `dbQMakeTable`Стол для макияжа

- `dbQDDL`Определение данных

- `dbQSQLPassThrough`Сквозной проезд

- `dbQSetOperation`Союза

- `dbQSPTBulk`Используется `dbQSQLPassThrough` для указания запроса, который не возвращает записи.

> [!NOTE]
> Для создания сквозного запроса S'L не `dbSQLPassThrough` устанавливайте константу. Это устанавливается автоматически движком базы данных Microsoft Jet при создании объекта запроса и установке строки соединения.

Для получения информации о [GetSQL](#getsql)строках S'L, см. Для получения информации о типах запросов [см.](#execute)

## <a name="cdaoquerydefisopen"></a><a name="isopen"></a>CDao-КуириДеф::IsOpen

Вызовите эту функцию `CDaoQueryDef` участника, чтобы определить, открыт ли объект в настоящее время.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `CDaoQueryDef` если объект в настоящее время открыт; в противном случае 0.

### <a name="remarks"></a>Remarks

Запрос должен находиться в открытом состоянии, прежде чем использовать его для вызова [выполнения](#execute) или создания объекта [CDaoRecordset.](../../mfc/reference/cdaorecordset-class.md) Для ввода вызова в открытый состояние либо [создать](#create) (для нового querydef) или [открыть](#open) (для существующего запроса).

## <a name="cdaoquerydefm_pdatabase"></a><a name="m_pdatabase"></a>CDao-КуириДеф::m_pDatabase

Содержит указатель на объект [CDaoDatabase,](../../mfc/reference/cdaodatabase-class.md) связанный с объектом querydef.

### <a name="remarks"></a>Remarks

Используйте этот указатель, если вам необходимо получить доступ к базе данных напрямую - например, для получения указателей на другие объекты запроса или записи в коллекциях базы данных.

## <a name="cdaoquerydefm_pdaoquerydef"></a><a name="m_pdaoquerydef"></a>CDao-КевириДеф::m_pDAOQueryDef

Содержит указатель на интерфейс OLE для базового объекта querydef DAO.

### <a name="remarks"></a>Remarks

Этот указатель обеспечивается для полноты и согласованности с другими классами. Однако, поскольку MFC довольно полностью инкапсулирует dAO querydefs, вы вряд ли в ней нуждается. Если вы используете его, делать это осторожно - в частности, не меняйте значение указателя, если вы не знаете, что вы делаете.

## <a name="cdaoquerydefopen"></a><a name="open"></a>CDao КуириДеф::Открыто

Вызовите эту функцию участника, чтобы открыть ранее сохраненный запрос в коллекции queryDefs базы данных.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Строка, содержащая имя сохраненного запроса для открытия. Вы можете использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Remarks

После того, как запрос открыт, можно вызвать [функцию](#execute) его выполнения или использовать запрос для создания объекта [CDaoRecordset.](../../mfc/reference/cdaorecordset-class.md)

## <a name="cdaoquerydefsetconnect"></a><a name="setconnect"></a>CDao-КуириДеф::SetConnect

Вызовите эту функцию участника, чтобы установить строку соединения объекта запроса.

```cpp
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Параметры

*lpszConnect*<br/>
Строка, содержащая строку соединения для связанного объекта [CDaoDatabase.](../../mfc/reference/cdaodatabase-class.md)

### <a name="remarks"></a>Remarks

Строка соединения используется для передачи дополнительной информации ODBC и некоторым драйверам ISAM по мере необходимости. Он не используется для Microsoft Jet (. MDB) баз данных.

> [!TIP]
> Предпочтительный способ работы со таблицами ODBC заключается в том, чтобы прикрепить их к . База данных MDB.

Перед выполнением запроса, представляющего сквозной запрос s'L к источнику данных ODBC, установите строку соединения и позвоните `SetConnect` [в SetReturnsRecords,](#setreturnsrecords) чтобы указать, возвращает ли запрос записи.

Для получения дополнительной информации о структуре строки соединения и примерах компонентов строки соединения см.

## <a name="cdaoquerydefsetname"></a><a name="setname"></a>CDao-КуириДеф::SetName

Позвоните в эту функцию участника, если вы хотите изменить имя querydef, которое не является временным.

```cpp
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Строка, содержащая новое имя для невременного запроса в связанном [объекте CDaoDatabase.](../../mfc/reference/cdaodatabase-class.md)

### <a name="remarks"></a>Remarks

Имена querydef являются уникальными, определяемыми пользователями именами. Вы можете `SetName` вызвать вызов до того, как объект querydef будет придучен к коллекции queryDefs.

## <a name="cdaoquerydefsetodbctimeout"></a><a name="setodbctimeout"></a>CDao-КуэриДеф::SetODBCTimeout

Вызов ими функции участника, чтобы установить ограничение по времени до того, как запрос к исходу источника данных ODBC отображался.

```cpp
void SetODBCTimeout(short nODBCTimeout);
```

### <a name="parameters"></a>Параметры

*nODBCTimeout*<br/>
Время ожидания запроса (в секундах).

### <a name="remarks"></a>Remarks

Эта функция члена позволяет переопределить число секунд по умолчанию до последующих операций на подключенном источнике данных "тайм-аут". Операция может быть временной из-за проблем с доступом к сети, чрезмерного времени обработки запросов и так далее. Вызов `SetODBCTimeout` перед выполнением запроса с помощью этого запроса, если требуется изменить значение тайм-аута запроса. (По мере повторного использования ODBC соединений значение тайм-аута одинаково для всех клиентов на одном и том же подключении.)

Значение по умолчанию для тайм-аутов запроса составляет 60 секунд.

## <a name="cdaoquerydefsetparamvalue"></a><a name="setparamvalue"></a>CDao-КуириДеф::SetParamValue

Вызовите эту функцию участника, чтобы установить значение параметра в querydef во время выполнения.

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
Имя параметра, значение которого вы хотите установить.

*varValue*<br/>
Значение для установки; увидеть замечания.

*Nindex*<br/>
Обординальное положение параметра в коллекции параметров querydef. Вы можете получить это значение с вызовами [getParameterCount](#getparametercount) и [GetParameterInfo](#getparameterinfo).

### <a name="remarks"></a>Remarks

Параметр уже был установлен в рамках строки запроса S'L. Вы можете получить доступ к параметру либо по имени, либо по его ординаторному положению в коллекции.

Укажите значение, установленное `COleVariant` как объект. Для получения информации об установлении желаемого [COleVariant](../../mfc/reference/colevariant-class.md)значения и вводе `COleVariant` объекта см.

## <a name="cdaoquerydefsetreturnsrecords"></a><a name="setreturnsrecords"></a>CDao-КуириДеф::SetReturnsRecords

Вызовите эту функцию участника как часть процесса настройки сквозного запроса s'L на внешнюю базу данных.

```cpp
void SetReturnsRecords(BOOL bReturnsRecords);
```

### <a name="parameters"></a>Параметры

*bReturnsRecords*<br/>
Передайте TRUE, если запрос на внешней базе данных возвращает записи; в противном случае, FALSE.

### <a name="remarks"></a>Remarks

В таком случае необходимо создать запрос и установить его `CDaoQueryDef` свойства с помощью других функций участника. Для описания внешних баз данных [см.](#setconnect)

## <a name="cdaoquerydefsetsql"></a><a name="setsql"></a>CDao-КуириДеф::SetS'L

Вызовите эту функцию участника, чтобы настроить выписку по s,L, которую выполняет запрос.

```cpp
void SetSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>Параметры

*lpszS'L*<br/>
Строка, содержащая полное заявление S'L, подходящее для выполнения. Синтаксис этой строки зависит от DBMS, на который нацелен ваш запрос. Для обсуждения синтаксиса, используемого в движке базы данных Microsoft Jet, см.

### <a name="remarks"></a>Remarks

Типичное использование `SetSQL` — это настройка объекта запроса для использования в сквозном запросе S'L. (Для синтаксиса сквозных запросов s'L на вашей целевой DBMS см.

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CDaoRecordset класс](../../mfc/reference/cdaorecordset-class.md)<br/>
[CDaoDatabase Класс](../../mfc/reference/cdaodatabase-class.md)<br/>
[Класс CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)<br/>
[Класс CDaoException](../../mfc/reference/cdaoexception-class.md)
