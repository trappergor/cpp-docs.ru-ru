---
title: Класс Кдаокуеридеф
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
ms.openlocfilehash: fabb8e957ffaf8ab8d9d57bca8e7835d366ac390
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231823"
---
# <a name="cdaoquerydef-class"></a>Класс Кдаокуеридеф

Представляет определение запроса или QueryDef, как правило, сохраненный в базе данных.

## <a name="syntax"></a>Синтаксис

```
class CDaoQueryDef : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Кдаокуеридеф:: Кдаокуеридеф](#cdaoquerydef)|Формирует объект `CDaoQueryDef`. Следующий вызов `Open` или `Create` , в зависимости от ваших потребностей.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[Кдаокуеридеф:: Append](#append)|Добавляет объект QueryDef к коллекции QueryDef базы данных в качестве сохраненного запроса.|
|[Кдаокуеридеф:: Канупдате](#canupdate)|Возвращает ненулевое значение, если запрос может обновить базу данных.|
|[Кдаокуеридеф:: Close](#close)|Закрывает объект QueryDef. Уничтожение объекта C++ по завершении работы с ним.|
|[Кдаокуеридеф:: Create](#create)|Создает базовый объект DAO QueryDef. Используйте QueryDef в качестве временного запроса или вызовите метод, `Append` чтобы сохранить его в базе данных.|
|[Кдаокуеридеф:: Execute](#execute)|Выполняет запрос, определенный объектом QueryDef.|
|[Кдаокуеридеф:: соединение](#getconnect)|Возвращает строку подключения, связанную с QueryDef. Строка подключения идентифицирует источник данных. (Только для транзитных запросов SQL; в противном случае — пустая строка.)|
|[Кдаокуеридеф:: Жетдатекреатед](#getdatecreated)|Возвращает дату создания сохраненного запроса.|
|[Кдаокуеридеф:: Жетдателаступдатед](#getdatelastupdated)|Возвращает дату последнего обновления сохраненного запроса.|
|[Кдаокуеридеф:: Жетфиелдкаунт](#getfieldcount)|Возвращает количество полей, определенных объектом QueryDef.|
|[Кдаокуеридеф:: Жетфиелдинфо](#getfieldinfo)|Возвращает сведения о указанном поле, определенном в запросе.|
|[Кдаокуеридеф:: Name](#getname)|Возвращает имя объекта QueryDef.|
|[Кдаокуеридеф:: Жетодбктимеаут](#getodbctimeout)|Возвращает значение времени ожидания, используемое ODBC (для запроса ODBC) при выполнении QueryDef. Определяет время, в течение которого будет разрешено выполнение действия запроса.|
|[Кдаокуеридеф:: GetParameterCount](#getparametercount)|Возвращает число параметров, определенных для запроса.|
|[Кдаокуеридеф:: GetParameterInfo](#getparameterinfo)|Возвращает сведения о указанном параметре в запрос.|
|[Кдаокуеридеф:: Жетпарамвалуе](#getparamvalue)|Возвращает значение указанного параметра для запроса.|
|[Кдаокуеридеф:: Жетрекордсаффектед](#getrecordsaffected)|Возвращает число записей, затронутых запросом действия.|
|[Кдаокуеридеф:: Жетретурнсрекордс](#getreturnsrecords)|Возвращает ненулевое значение, если запрос, определяемый объектом QueryDef, возвращает записи.|
|[Кдаокуеридеф:: Жетскл](#getsql)|Возвращает строку SQL, указывающую запрос, определенный объектом QueryDef.|
|[Кдаокуеридеф:: GetType](#gettype)|Возвращает тип запроса: удаление, обновление, добавление, создание таблицы и т. д.|
|[Кдаокуеридеф:: OnOpen](#isopen)|Возвращает ненулевое значение, если объект QueryDef открыт и может быть выполнен.|
|[Кдаокуеридеф:: Open](#open)|Открывает существующий объект QueryDef, хранящийся в коллекции QueryDef базы данных.|
|[Кдаокуеридеф:: Сетконнект](#setconnect)|Задает строку подключения для SQL-запроса к серверу в источнике данных ODBC.|
|[Кдаокуеридеф:: SetName](#setname)|Задает имя сохраненного запроса, заменяя имя, которое используется при создании объекта QueryDef.|
|[Кдаокуеридеф:: Сетодбктимеаут](#setodbctimeout)|Задает значение времени ожидания, используемое ODBC (для запроса ODBC) при выполнении QueryDef.|
|[Кдаокуеридеф:: Сетпарамвалуе](#setparamvalue)|Задает значение указанного параметра для запроса.|
|[Кдаокуеридеф:: Сетретурнсрекордс](#setreturnsrecords)|Указывает, возвращает ли объект QueryDef записи. Присвоение этому атрибуту значения TRUE допускается только для запросов к серверу SQL.|
|[Кдаокуеридеф:: Сетскл](#setsql)|Задает строку SQL, указывающую запрос, определенный объектом QueryDef.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Кдаокуеридеф:: m_pDAOQueryDef](#m_pdaoquerydef)|Указатель на интерфейс OLE для базового объекта DAO QueryDef.|
|[Кдаокуеридеф:: m_pDatabase](#m_pdatabase)|Указатель на объект, `CDaoDatabase` с которым связан элемент QueryDef. Объект QueryDef может быть сохранен в базе данных или нет.|

## <a name="remarks"></a>Remarks

QueryDef — это объект доступа к данным, содержащий инструкцию SQL, которая описывает запрос, и его свойства, такие как "Дата создания" и "время ожидания ODBC". Кроме того, можно создавать временные объекты QueryDef, не сохраняя их, но это удобно и намного более эффективно — для сохранения часто используемых запросов в базе данных. Объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) поддерживает коллекцию, называемую коллекцией QueryDefs, которая содержит сохраненные объекты QueryDef.

> [!NOTE]
> Классы базы данных DAO отличаются от классов баз данных MFC, основанных на открытом подключении к базам данных (ODBC). Все имена классов баз данных DAO имеют префикс "Кдао". Вы по-прежнему можете обращаться к источникам данных ODBC с помощью классов DAO. Как правило, классы MFC, основанные на DAO, более поддерживаются, чем классы MFC, основанные на ODBC; классы на основе DAO могут обращаться к данным, включая драйверы ODBC, через собственное ядро СУБД. Классы на основе DAO также поддерживают операции языка DDL, такие как добавление таблиц через классы, без необходимости непосредственного вызова DAO.

## <a name="usage"></a>Использование

Объекты QueryDef можно использовать для работы с существующим сохраненным запросом или для создания нового сохраненного запроса или временного запроса.

1. Во всех случаях сначала создайте `CDaoQueryDef` объект, указав указатель на объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) , которому принадлежит запрос.

1. Затем выполните следующие действия в зависимости от того, что вам нужно:

   - Чтобы использовать существующий сохраненный запрос, вызовите функцию [Open](#open) Member объекта QueryDef, указав имя сохраненного запроса.

   - Чтобы создать новый сохраненный запрос, вызовите функцию [-член объекта](#create) QueryDef, указав имя запроса. Затем вызовите [append](#append) , чтобы сохранить запрос, добавив его в коллекцию QueryDef базы данных. `Create`помещает QueryDef в открытое состояние, поэтому после вызова метода `Create` не вызывается `Open` .

   - Чтобы создать временный объект QueryDef, вызовите `Create` . Передайте пустую строку для имени запроса. Не вызывайте `Append`.

По завершении использования объекта QueryDef вызовите его функцию-член [Close](#close) . затем уничтожайте объект QueryDef.

> [!TIP]
> Самый простой способ создать сохраненные запросы — создать их и сохранить в базе данных с помощью Microsoft Access. Затем их можно открыть и использовать в коде MFC.

## <a name="purposes"></a>Целях

Объект QueryDef можно использовать в следующих целях:

- Создание `CDaoRecordset` объекта

- Вызов функции-члена объекта `Execute` для непосредственного выполнения запроса действия или запроса к серверу SQL

Объект QueryDef можно использовать для любого типа запросов, включая SELECT, Action, перекрестный, DELETE, Update, Append, Make-Table, Definition, а также запросы SQL Pass, Union и массовы. Тип запроса определяется содержимым предоставленной инструкции SQL. Сведения о типах запросов см. в разделе `Execute` функции и члены [GetType](#gettype) . Наборы записей обычно используются для запросов, возвращающих строки, обычно с помощью инструкции **SELECT... ИЗ** ключевых слов. `Execute`чаще всего используется для выполнения операций с массовыми операциями. Дополнительные сведения см. в разделе [EXECUTE](#execute) and [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

## <a name="querydefs-and-recordsets"></a>QueryDef и наборы записей

Чтобы использовать объект QueryDef для создания `CDaoRecordset` объекта, обычно создается или открывается объект QueryDef, как описано выше. Затем создайте объект набора записей, передав указатель на объект QueryDef при вызове [CDaoRecordset:: Open](../../mfc/reference/cdaorecordset-class.md#open). Передаваемый объект QueryDef должен находиться в открытом состоянии. Дополнительные сведения см. в разделе Class [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Нельзя использовать QueryDef для создания набора записей (наиболее распространенный способ использования для объекта QueryDef), если он не находится в открытом состоянии. Переведите QueryDef в открытое состояние, вызвав либо `Open` или `Create` .

## <a name="external-databases"></a>Внешние базы данных

Объекты QueryDef являются предпочтительным способом использования собственного диалекта SQL внешнего компонента базы данных. Например, можно создать запрос Transact SQL (используемый в Microsoft SQL Server) и сохранить его в объекте QueryDef. Если необходимо использовать SQL-запрос, не основанный на ядре СУБД Microsoft Jet, необходимо указать строку подключения, указывающую на внешний источник данных. Запросы с допустимыми строками соединения пропускают ядро СУБД и передают запрос непосредственно серверу внешней базы данных для обработки.

> [!TIP]
> Предпочтительный способ работы с таблицами ODBC — присоединить их к Microsoft Jet (. MDB) база данных.

Связанные сведения см. в разделах «объект QueryDef», «коллекция QueryDef» и «объект Кдбдатабасе» в пакете SDK DAO.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDaoQueryDef`

## <a name="requirements"></a>Требования

**Заголовок:** афксдао. h

## <a name="cdaoquerydefappend"></a><a name="append"></a>Кдаокуеридеф:: Append

Вызовите эту функцию-член после вызова метода [CREATE](#create) для создания нового объекта QueryDef.

```
virtual void Append();
```

### <a name="remarks"></a>Remarks

`Append`сохраняет объекты QueryDef в базе данных, добавляя объект в коллекцию QueryDef базы данных. Объект QueryDef можно использовать в качестве временного объекта, не добавляя его, но если его нужно сохранить, необходимо вызвать `Append` .

При попытке добавить временный объект QueryDef MFC выдает исключение типа [кдаоексцептион](../../mfc/reference/cdaoexception-class.md).

## <a name="cdaoquerydefcanupdate"></a><a name="canupdate"></a>Кдаокуеридеф:: Канупдате

Вызовите эту функцию-член, чтобы определить, можно ли изменить QueryDef, например изменить ее имя или строку SQL.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если разрешено изменение QueryDef; в противном случае — 0.

### <a name="remarks"></a>Remarks

Можно изменить объект QueryDef, если:

- Он не основан на базе данных, открытой только для чтения.

- У вас есть разрешения на обновление базы данных.

   Это зависит от того, реализованы ли функции безопасности. MFC не обеспечивает поддержку безопасности; его необходимо реализовать самостоятельно путем непосредственного вызова DAO или с помощью Microsoft Access. См. раздел "свойство Permissions" в справке DAO.

## <a name="cdaoquerydefcdaoquerydef"></a><a name="cdaoquerydef"></a>Кдаокуеридеф:: Кдаокуеридеф

Формирует объект `CDaoQueryDef`.

```
CDaoQueryDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Параметры

*пдатабасе*<br/>
Указатель на открытый объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) .

### <a name="remarks"></a>Remarks

Объект может представлять существующий QueryDef, хранящийся в коллекции QueryDef базы данных, новый запрос, хранящийся в коллекции, или временный запрос, который не должен храниться. Следующий шаг зависит от типа QueryDef:

- Если объект представляет существующий QueryDef, вызовите функцию [открытого](#open) члена объекта, чтобы инициализировать ее.

- Если объект представляет новый QueryDef для сохранения, вызовите функцию-член [CREATE](#create) объекта. При этом объект добавляется в коллекцию QueryDef базы данных. Затем вызывайте `CDaoQueryDef` функции члена, чтобы задать атрибуты объекта. Наконец, вызовите [append](#append).

- Если объект представляет временный QueryDef (не сохраняемый в базе данных), вызовите метод `Create` , передав пустую строку для имени запроса. После вызова `Create` инициализируйте объект QueryDef, указав его атрибуты напрямую. Не вызывайте `Append`.

Чтобы задать атрибуты объекта QueryDef, можно использовать функции элементов [SetName](#setname), [сетскл](#setsql), [сетконнект](#setconnect), [сетодбктимеаут](#setodbctimeout)и [сетретурнсрекордс](#setreturnsrecords) .

По завершении работы с объектом QueryDef вызовите его [закрытую](#close) функцию Member. Если у вас есть указатель на QueryDef, используйте **`delete`** оператор для уничтожения объекта C++.

## <a name="cdaoquerydefclose"></a><a name="close"></a>Кдаокуеридеф:: Close

Вызовите эту функцию члена, когда завершите использование объекта QueryDef.

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

Закрытие объекта QueryDef освобождает базовый объект DAO, но не уничтожает сохраненный объект DAO QueryDef или `CDaoQueryDef` объект C++. Это не то же самое, что [CDaoDatabase::D елетекуеридеф](../../mfc/reference/cdaodatabase-class.md#deletequerydef), который удаляет QueryDef из коллекции QueryDef базы данных в DAO (если не является временным QueryDef).

## <a name="cdaoquerydefcreate"></a><a name="create"></a>Кдаокуеридеф:: Create

Вызовите эту функцию-член, чтобы создать новый сохраненный запрос или новый временный запрос.

```
virtual void Create(
    LPCTSTR lpszName = NULL,
    LPCTSTR lpszSQL = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
Уникальное имя запроса, сохраненное в базе данных. Дополнительные сведения о строке см. в разделе «метод Креатекуеридеф» справки DAO. Если вы принимаете значение по умолчанию (пустая строка), создается временный объект QueryDef. Такой запрос не сохраняется в коллекции QueryDef.

*lpszSQL*<br/>
Строка SQL, определяющая запрос. Если вы принимаете значение по умолчанию NULL, для установки строки необходимо вызвать [сетскл](#setsql) . До этого запрос не определен. Однако можно использовать неопределенный запрос для открытия набора записей; Дополнительные сведения см. в разделе Примечания. Инструкция SQL должна быть определена до того, как можно будет добавить QueryDef в коллекцию QueryDef.

### <a name="remarks"></a>Remarks

Если имя передается в *лпсзнаме*, можно вызвать [append](#append) , чтобы сохранить QueryDef в коллекции QueryDef базы данных. В противном случае объект является временным объектом QueryDef и не сохраняется. В любом случае объект QueryDef находится в открытом состоянии, и его можно использовать для создания объекта [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) или вызова функции [выполнения](#execute) элемента QueryDef.

Если инструкция SQL не указана в параметре *lpszSQL*, то нельзя выполнить запрос с помощью, `Execute` но можно использовать его для создания набора записей. В этом случае MFC использует инструкцию SQL набора записей по умолчанию.

## <a name="cdaoquerydefexecute"></a><a name="execute"></a>Кдаокуеридеф:: Execute

Вызовите эту функцию члена, чтобы выполнить запрос, определенный объектом QueryDef.

```
virtual void Execute(int nOptions = dbFailOnError);
```

### <a name="parameters"></a>Параметры

*ноптионс*<br/>
Целое число, определяющее характеристики запроса. Связанные сведения см. в разделе "выполнение метода" справки DAO. Чтобы объединить следующие константы для этого аргумента, можно использовать оператор побитового или ( **&#124;**):

- `dbDenyWrite`Запретите разрешение на запись другим пользователям.

- `dbInconsistent`Непоследовательные обновления.

- `dbConsistent`Последовательные обновления.

- `dbSQLPassThrough`Сквозная передача SQL. Вызывает передачу инструкции SQL в базу данных ODBC для обработки.

- `dbFailOnError`Значение по умолчанию. Выполните откат обновлений при возникновении ошибки и сообщите пользователю об ошибке.

- `dbSeeChanges`Создавать ошибку времени выполнения, если измененные данные изменяются другим пользователем.

> [!NOTE]
> Описание терминов «не согласуется» и «consistent» см. в разделе «выполнение метода» справки DAO.

### <a name="remarks"></a>Remarks

Объекты QueryDef, используемые для выполнения таким образом, могут представлять только один из следующих типов запросов:

- Запросы действий

- Запросы к серверу SQL

`Execute`не работает для запросов, возвращающих записи, таких как запросы SELECT. `Execute`обычно используется для запросов с массовыми операциями, таких как **Обновление**, **Вставка**или **Выбор в**, или для операций языка описания данных (DDL).

> [!TIP]
> Предпочтительным способом работы с источниками данных ODBC является присоединение таблиц к Microsoft Jet (. MDB) база данных. Дополнительные сведения см. в разделе «доступ к внешним базам данных с помощью DAO» справки DAO.

Вызовите функцию члена [жетрекордсаффектед](#getrecordsaffected) объекта QueryDef, чтобы определить количество записей, затронутых последним `Execute` вызовом. Например, `GetRecordsAffected` возвращает сведения о количестве записей, удаленных, обновленных или вставленных при выполнении запроса действия. Возвращенное число не будет отражать изменения в связанных таблицах, если действуют каскадные обновления или удаления.

Если включить `dbInconsistent` и, и `dbConsistent` , или, если не указано ни одного, результатом будет значение по умолчанию, `dbInconsistent` .

`Execute`не возвращает набор записей. Использование `Execute` в запросе, выбирающем записи, приводит к тому, что MFC создает исключение типа [кдаоексцептион](../../mfc/reference/cdaoexception-class.md).

## <a name="cdaoquerydefgetconnect"></a><a name="getconnect"></a>Кдаокуеридеф:: соединение

Вызовите эту функцию члена, чтобы получить строку подключения, связанную с источником данных объекта QueryDef.

```
CString GetConnect();
```

### <a name="return-value"></a>Возвращаемое значение

Значение [CString](../../atl-mfc-shared/reference/cstringt-class.md) , содержащее строку подключения для QueryDef.

### <a name="remarks"></a>Remarks

Эта функция используется только с источниками данных ODBC и некоторыми драйверами ISAM. Он не используется с Microsoft Jet (. MDB); в этом случае `GetConnect` возвращает пустую строку. Дополнительные сведения см. в разделе [сетконнект](#setconnect).

> [!TIP]
> Предпочтительный способ работы с таблицами ODBC — присоединить их к. База данных MDB. Дополнительные сведения см. в разделе «доступ к внешним базам данных с помощью DAO» справки DAO.

Сведения о строках подключения см. в разделе "свойство Connect" справки DAO.

## <a name="cdaoquerydefgetdatecreated"></a><a name="getdatecreated"></a>Кдаокуеридеф:: Жетдатекреатед

Вызовите эту функцию члена, чтобы получить дату создания объекта QueryDef.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , содержащий дату и время создания объекта QueryDef.

### <a name="remarks"></a>Remarks

Связанные сведения см. в подразделе «DateCreated, свойства LastUpdated» справки DAO.

## <a name="cdaoquerydefgetdatelastupdated"></a><a name="getdatelastupdated"></a>Кдаокуеридеф:: Жетдателаступдатед

Вызовите эту функцию-член для получения даты последнего обновления объекта QueryDef — при изменении любого из его свойств, например его имени, строки SQL или его строки подключения.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Возвращаемое значение

Объект [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) , содержащий дату и время последнего обновления объекта QueryDef.

### <a name="remarks"></a>Remarks

Связанные сведения см. в подразделе «DateCreated, свойства LastUpdated» справки DAO.

## <a name="cdaoquerydefgetfieldcount"></a><a name="getfieldcount"></a>Кдаокуеридеф:: Жетфиелдкаунт

Вызовите эту функцию члена, чтобы получить количество полей в запросе.

```
short GetFieldCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число полей, определенных в запросе.

### <a name="remarks"></a>Remarks

`GetFieldCount`полезен для цикла по всем полям в QueryDef. Для этой цели используйте `GetFieldCount` в сочетании с [жетфиелдинфо](#getfieldinfo).

## <a name="cdaoquerydefgetfieldinfo"></a><a name="getfieldinfo"></a>Кдаокуеридеф:: Жетфиелдинфо

Вызывайте эту функцию-член для получения различных видов информации о поле, определенном в QueryDef.

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

*ниндекс*<br/>
Отсчитываемый от нуля индекс требуемого поля в коллекции полей QueryDef для поиска по индексу.

*FieldInfo*<br/>
Ссылка на `CDaoFieldInfo` объект, который возвращает запрошенную информацию.

*двинфуптионс*<br/>
Параметры, указывающие, какие сведения о поле следует извлечь. Ниже перечислены доступные параметры, а также то, что вызывает возврат функции.

- Имя, тип, размер, атрибуты AFX_DAO_PRIMARY_INFO (по умолчанию)

- AFX_DAO_SECONDARY_INFO первичной информации, а также: порядковый номер, обязательный, допускающий нулевую длину, исходное поле, внешнее имя, исходная таблица, порядок сортировки

- AFX_DAO_ALL_INFO первичной и дополнительной информации плюс: значение по умолчанию, текст проверки, правило проверки

*лпсзнаме*<br/>
Строка, содержащая имя нужного поля для поиска по имени. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Remarks

Описание сведений, возвращаемых в *FieldInfo*, см. в разделе Структура [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) . Эта структура содержит элементы, соответствующие описательным данным в разделе *двинфуптионс* выше. Если вы запрашиваете один уровень информации, вы также получаете все предыдущие уровни информации.

## <a name="cdaoquerydefgetname"></a><a name="getname"></a>Кдаокуеридеф:: Name

Вызовите эту функцию члена, чтобы получить имя запроса, представленного объектом QueryDef.

```
CString GetName();
```

### <a name="return-value"></a>Возвращаемое значение

Имя запроса.

### <a name="remarks"></a>Remarks

Имена QueryDef являются уникальными определяемыми пользователем именами. Дополнительные сведения о именах QueryDef см. в разделе "свойство Name" справки DAO.

## <a name="cdaoquerydefgetodbctimeout"></a><a name="getodbctimeout"></a>Кдаокуеридеф:: Жетодбктимеаут

Вызовите эту функцию-член, чтобы получить текущее ограничение времени до истечения времени ожидания запроса к источнику данных ODBC.

```
short GetODBCTimeout();
```

### <a name="return-value"></a>Возвращаемое значение

Время ожидания запроса (в секундах).

### <a name="remarks"></a>Remarks

Сведения об этом ограничении времени см. в разделе "свойство Одбктимеаут" справки DAO.

> [!TIP]
> Предпочтительный способ работы с таблицами ODBC — присоединить их к Microsoft Jet (. MDB) база данных. Дополнительные сведения см. в разделе «доступ к внешним базам данных с помощью DAO» справки DAO.

## <a name="cdaoquerydefgetparametercount"></a><a name="getparametercount"></a>Кдаокуеридеф:: GetParameterCount

Вызовите эту функцию члена, чтобы получить количество параметров в сохраненном запросе.

```
short GetParameterCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число параметров, определенных в запросе.

### <a name="remarks"></a>Remarks

`GetParameterCount`полезен для циклического прохода по всем параметрам в QueryDef. Для этой цели используйте `GetParameterCount` в сочетании с [GetParameterInfo](#getparameterinfo).

Дополнительные сведения см. в разделах "объект параметров", "Коллекция параметров" и "объявление параметров (SQL)" в справке DAO.

## <a name="cdaoquerydefgetparameterinfo"></a><a name="getparameterinfo"></a>Кдаокуеридеф:: GetParameterInfo

Вызовите эту функцию-член для получения сведений о параметре, определенном в QueryDef.

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

*ниндекс*<br/>
Отсчитываемый от нуля индекс требуемого параметра в коллекции параметров объекта QueryDef для поиска по индексу.

*параминфо*<br/>
Ссылка на объект [кдаопараметеринфо](../../mfc/reference/cdaoparameterinfo-structure.md) , который возвращает запрошенную информацию.

*двинфуптионс*<br/>
Параметры, указывающие, какие сведения о параметре необходимо получить. Параметр доступен здесь вместе с тем, что приводит к возврату функции:

- Имя AFX_DAO_PRIMARY_INFO (по умолчанию), введите

*лпсзнаме*<br/>
Строка, содержащая имя требуемого параметра для поиска по имени. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Remarks

Описание сведений, возвращаемых в *параминфо*, см. в разделе Структура [кдаопараметеринфо](../../mfc/reference/cdaoparameterinfo-structure.md) . Эта структура содержит элементы, соответствующие описательным данным в разделе *двинфуптионс* выше.

Дополнительные сведения см. в подразделе «объявление параметров (SQL)» справки DAO.

## <a name="cdaoquerydefgetparamvalue"></a><a name="getparamvalue"></a>Кдаокуеридеф:: Жетпарамвалуе

Вызовите эту функцию члена, чтобы получить текущее значение указанного параметра, хранящегося в коллекции параметров объекта QueryDef.

```
virtual COleVariant GetParamValue(LPCTSTR lpszName);
virtual COleVariant GetParamValue(int nIndex);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
Имя параметра, значение которого требуется для поиска по имени.

*ниндекс*<br/>
Отсчитываемый от нуля индекс параметра в коллекции параметров объекта QueryDef для поиска по индексу. Это значение можно получить с помощью вызовов [GetParameterCount](#getparametercount) и [GetParameterInfo](#getparameterinfo).

### <a name="return-value"></a>Возвращаемое значение

Объект класса [COleVariant](../../mfc/reference/colevariant-class.md) , содержащий значение параметра.

### <a name="remarks"></a>Remarks

Доступ к параметру можно получить по имени или по порядковому номеру в коллекции.

Дополнительные сведения см. в подразделе «объявление параметров (SQL)» справки DAO.

## <a name="cdaoquerydefgetrecordsaffected"></a><a name="getrecordsaffected"></a>Кдаокуеридеф:: Жетрекордсаффектед

Вызовите эту функцию члена, чтобы определить, сколько записей было затронуто при последнем вызове [EXECUTE](#execute).

```
long GetRecordsAffected();
```

### <a name="return-value"></a>Возвращаемое значение

Количество обработанных записей.

### <a name="remarks"></a>Remarks

Возвращенное число не будет отражать изменения в связанных таблицах, если действуют каскадные обновления или удаления.

Связанные сведения см. в разделе «свойство Рекордсаффектед» справки DAO.

## <a name="cdaoquerydefgetreturnsrecords"></a><a name="getreturnsrecords"></a>Кдаокуеридеф:: Жетретурнсрекордс

Вызовите эту функцию-член, чтобы определить, основан ли объект QueryDef на запросе, возвращающем записи.

```
BOOL GetReturnsRecords();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если QueryDef основан на запросе, возвращающем записи; в противном случае — 0.

### <a name="remarks"></a>Remarks

Эта функция-член используется только для запросов к серверу SQL. Дополнительные сведения о запросах SQL см. в описании функции [выполнения](#execute) члена. Дополнительные сведения о работе с передаваемыми запросами SQL см. в описании функции-члена [сетретурнсрекордс](#setreturnsrecords) .

Связанные сведения см. в разделе "свойство ReturnsRecords" справки DAO.

## <a name="cdaoquerydefgetsql"></a><a name="getsql"></a>Кдаокуеридеф:: Жетскл

Вызовите эту функцию-член, чтобы получить инструкцию SQL, определяющую запрос, на котором основывается объект QueryDef.

```
CString GetSQL();
```

### <a name="return-value"></a>Возвращаемое значение

Инструкция SQL, определяющая запрос, на котором основана QueryDef.

### <a name="remarks"></a>Remarks

Затем, вероятно, будет проанализирована строка для ключевых слов, имен таблиц и т. д.

Дополнительные сведения см. в подразделах «свойство SQL», «сравнение Microsoft Jet ядро СУБД SQL и ANSI SQL» и «запрос базы данных с SQL в коде» справки DAO.

## <a name="cdaoquerydefgettype"></a><a name="gettype"></a>Кдаокуеридеф:: GetType

Вызовите эту функцию члена, чтобы определить тип запроса QueryDef.

```
short GetType();
```

### <a name="return-value"></a>Возвращаемое значение

Тип запроса, определяемого объектом QueryDef. Значения см. в разделе Примечания.

### <a name="remarks"></a>Remarks

Тип запроса задается тем, что указывается в строке SQL объекта QueryDef при создании объекта QueryDef, или при вызове функции-члена [сетскл](#setsql) существующего объекта QueryDef. Тип запроса, возвращаемый этой функцией, может иметь одно из следующих значений:

- `dbQSelect`Метьте

- Действие `dbQAction`

- `dbQCrosstab`Запросов

- `dbQDelete` Delete

- `dbQUpdate` Update

- `dbQAppend`Добавление

- `dbQMakeTable`Make-Table

- `dbQDDL`Определение данных

- `dbQSQLPassThrough`Сквозная передача

- `dbQSetOperation`Наборов

- `dbQSPTBulk`Используется с `dbQSQLPassThrough` для указания запроса, который не возвращает записи.

> [!NOTE]
> Чтобы создать запрос к серверу SQL, не устанавливайте `dbSQLPassThrough` константу. Он задается автоматически ядром базы данных Microsoft Jet при создании объекта QueryDef и задании строки подключения.

Дополнительные сведения о строках SQL см. в разделе [жетскл](#getsql). Дополнительные сведения о типах запросов см. в разделе [EXECUTE](#execute).

## <a name="cdaoquerydefisopen"></a><a name="isopen"></a>Кдаокуеридеф:: OnOpen

Вызовите эту функцию-член, чтобы определить `CDaoQueryDef` , открыт ли объект в данный момент.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если `CDaoQueryDef` объект открыт в данный момент; в противном случае — 0.

### <a name="remarks"></a>Remarks

Объект QueryDef должен находиться в открытом состоянии, прежде чем использовать его для вызова [EXECUTE](#execute) или для создания объекта [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) . Чтобы разместить QueryDef в вызове открытого состояния, [Создайте](#create) (для нового объекта QueryDef) или [откройте](#open) (для существующего объекта QueryDef).

## <a name="cdaoquerydefm_pdatabase"></a><a name="m_pdatabase"></a>Кдаокуеридеф:: m_pDatabase

Содержит указатель на объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) , связанный с объектом QueryDef.

### <a name="remarks"></a>Remarks

Используйте этот указатель, если требуется напрямую обращаться к базе данных, например для получения указателей на другие объекты QueryDef или Recordset в коллекциях базы данных.

## <a name="cdaoquerydefm_pdaoquerydef"></a><a name="m_pdaoquerydef"></a>Кдаокуеридеф:: m_pDAOQueryDef

Содержит указатель на интерфейс OLE для базового объекта DAO QueryDef.

### <a name="remarks"></a>Remarks

Этот указатель предоставляется для полноты и согласованности с другими классами. Однако, поскольку MFC, скорее, полностью инкапсулирует объекты DAO, вам вряд ли это понадобится. Если вы используете его, сделайте это осторожно — в частности, не изменяйте значение указателя, если вы не уверены, что делаете.

## <a name="cdaoquerydefopen"></a><a name="open"></a>Кдаокуеридеф:: Open

Вызовите эту функцию-член, чтобы открыть объект QueryDef, сохраненный ранее в коллекции QueryDef базы данных.

```
virtual void Open(LPCTSTR lpszName = NULL);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
Строка, содержащая имя сохраненного объекта QueryDef. Можно использовать [CString](../../atl-mfc-shared/reference/cstringt-class.md).

### <a name="remarks"></a>Remarks

После открытия QueryDef можно вызвать функцию [EXECUTE](#execute) -Member или использовать QueryDef для создания объекта [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) .

## <a name="cdaoquerydefsetconnect"></a><a name="setconnect"></a>Кдаокуеридеф:: Сетконнект

Вызовите эту функцию члена, чтобы задать строку соединения объекта QueryDef.

```cpp
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Параметры

*лпсзконнект*<br/>
Строка, содержащая строку соединения для связанного объекта [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) .

### <a name="remarks"></a>Remarks

Строка подключения используется для передачи дополнительных сведений в ODBC и определенных драйверах ISAM при необходимости. Он не используется для Microsoft Jet (. MDB) базы данных.

> [!TIP]
> Предпочтительный способ работы с таблицами ODBC — присоединить их к. База данных MDB.

Перед выполнением объекта QueryDef, представляющего транзитный запрос SQL к источнику данных ODBC, задайте строку подключения с помощью `SetConnect` метода и вызовите [сетретурнсрекордс](#setreturnsrecords) , чтобы указать, будет ли запрос возвращать записи.

Дополнительные сведения о структуре строки подключения и примеры компонентов строки подключения см. в разделе "свойство Connect" справки DAO.

## <a name="cdaoquerydefsetname"></a><a name="setname"></a>Кдаокуеридеф:: SetName

Вызовите эту функцию-член, если необходимо изменить имя объекта QueryDef, который не является временным.

```cpp
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
Строка, содержащая новое имя для невременных запросов в связанном объекте [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) .

### <a name="remarks"></a>Remarks

Имена QueryDef являются уникальными, определяемыми пользователем именами. `SetName`Перед добавлением объекта QueryDef в коллекцию QueryDef можно вызвать метод.

## <a name="cdaoquerydefsetodbctimeout"></a><a name="setodbctimeout"></a>Кдаокуеридеф:: Сетодбктимеаут

Вызовите эту функцию-член, чтобы установить предельное время до истечения времени ожидания запроса к источнику данных ODBC.

```cpp
void SetODBCTimeout(short nODBCTimeout);
```

### <a name="parameters"></a>Параметры

*нодбктимеаут*<br/>
Время ожидания запроса (в секундах).

### <a name="remarks"></a>Remarks

Эта функция члена позволяет переопределить количество секунд по умолчанию перед выполнением последующих операций в подключенном источнике данных "время ожидания". Время ожидания операции может истекает из-за проблем с доступом к сети, чрезмерного времени обработки запросов и т. д. Вызовите метод `SetODBCTimeout` перед выполнением запроса с этим объектом QueryDef, если необходимо изменить значение времени ожидания запроса. (Так как ODBC повторно использует соединения, значение времени ожидания одинаково для всех клиентов в одном соединении.)

Значение времени ожидания запроса по умолчанию составляет 60 секунд.

## <a name="cdaoquerydefsetparamvalue"></a><a name="setparamvalue"></a>Кдаокуеридеф:: Сетпарамвалуе

Вызовите эту функцию-член, чтобы задать значение параметра в QueryDef во время выполнения.

```
virtual void SetParamValue(
    LPCTSTR lpszName,
    const COleVariant& varValue);

virtual void SetParamValue(
    int nIndex,
    const COleVariant& varValue);
```

### <a name="parameters"></a>Параметры

*лпсзнаме*<br/>
Имя параметра, значение которого необходимо задать.

*varValue*<br/>
Заданное значение; см. раздел Примечания.

*ниндекс*<br/>
Порядковый номер параметра в коллекции параметров QueryDef. Это значение можно получить с помощью вызовов [GetParameterCount](#getparametercount) и [GetParameterInfo](#getparameterinfo).

### <a name="remarks"></a>Remarks

Параметр должен быть уже установлен в составе строки SQL объекта QueryDef. Доступ к параметру можно получить по имени или по порядковому номеру в коллекции.

Укажите значение, которое необходимо задать в качестве `COleVariant` объекта. Сведения о настройке требуемого значения и типа в `COleVariant` объекте см. в разделе Class [COleVariant](../../mfc/reference/colevariant-class.md).

## <a name="cdaoquerydefsetreturnsrecords"></a><a name="setreturnsrecords"></a>Кдаокуеридеф:: Сетретурнсрекордс

Вызовите эту функцию-член в рамках процесса настройки запроса к серверу SQL во внешнюю базу данных.

```cpp
void SetReturnsRecords(BOOL bReturnsRecords);
```

### <a name="parameters"></a>Параметры

*бретурнсрекордс*<br/>
Передать значение TRUE, если запрос во внешней базе данных возвращает записи; в противном случае — значение FALSE.

### <a name="remarks"></a>Remarks

В этом случае необходимо создать QueryDef и задать его свойства с помощью других `CDaoQueryDef` функций-членов. Описание внешних баз данных см. в разделе [сетконнект](#setconnect).

## <a name="cdaoquerydefsetsql"></a><a name="setsql"></a>Кдаокуеридеф:: Сетскл

Вызовите эту функцию члена, чтобы задать инструкцию SQL, выполняемую объектом QueryDef.

```cpp
void SetSQL(LPCTSTR lpszSQL);
```

### <a name="parameters"></a>Параметры

*lpszSQL*<br/>
Строка, содержащая полную инструкцию SQL, подходящую для выполнения. Синтаксис этой строки зависит от СУБД, для которой предназначен запрос. Описание синтаксиса, используемого в ядре СУБД Microsoft Jet, см. в разделе «Создание инструкций SQL в коде» справки DAO.

### <a name="remarks"></a>Remarks

Типичное использование `SetSQL` — Настройка объекта QueryDef для использования в запросе к серверу SQL. (Синтаксис запросов SQL, передаваемых в целевую СУБД, см. в документации по СУБД.)

## <a name="see-also"></a>См. также раздел

[CObject, класс](../../mfc/reference/cobject-class.md)<br/>
[Иерархическая диаграмма](../../mfc/hierarchy-chart.md)<br/>
[Класс CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)<br/>
[Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)<br/>
[Класс Кдаотабледеф](../../mfc/reference/cdaotabledef-class.md)<br/>
[Класс Кдаоексцептион](../../mfc/reference/cdaoexception-class.md)
