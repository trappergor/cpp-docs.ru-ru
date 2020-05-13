---
title: Класс CDaoTableDef
ms.date: 11/04/2016
f1_keywords:
- CDaoTableDef
- AFXDAO/CDaoTableDef
- AFXDAO/CDaoTableDef::CDaoTableDef
- AFXDAO/CDaoTableDef::Append
- AFXDAO/CDaoTableDef::CanUpdate
- AFXDAO/CDaoTableDef::Close
- AFXDAO/CDaoTableDef::Create
- AFXDAO/CDaoTableDef::CreateField
- AFXDAO/CDaoTableDef::CreateIndex
- AFXDAO/CDaoTableDef::DeleteField
- AFXDAO/CDaoTableDef::DeleteIndex
- AFXDAO/CDaoTableDef::GetAttributes
- AFXDAO/CDaoTableDef::GetConnect
- AFXDAO/CDaoTableDef::GetDateCreated
- AFXDAO/CDaoTableDef::GetDateLastUpdated
- AFXDAO/CDaoTableDef::GetFieldCount
- AFXDAO/CDaoTableDef::GetFieldInfo
- AFXDAO/CDaoTableDef::GetIndexCount
- AFXDAO/CDaoTableDef::GetIndexInfo
- AFXDAO/CDaoTableDef::GetName
- AFXDAO/CDaoTableDef::GetRecordCount
- AFXDAO/CDaoTableDef::GetSourceTableName
- AFXDAO/CDaoTableDef::GetValidationRule
- AFXDAO/CDaoTableDef::GetValidationText
- AFXDAO/CDaoTableDef::IsOpen
- AFXDAO/CDaoTableDef::Open
- AFXDAO/CDaoTableDef::RefreshLink
- AFXDAO/CDaoTableDef::SetAttributes
- AFXDAO/CDaoTableDef::SetConnect
- AFXDAO/CDaoTableDef::SetName
- AFXDAO/CDaoTableDef::SetSourceTableName
- AFXDAO/CDaoTableDef::SetValidationRule
- AFXDAO/CDaoTableDef::SetValidationText
- AFXDAO/CDaoTableDef::m_pDAOTableDef
- AFXDAO/CDaoTableDef::m_pDatabase
helpviewer_keywords:
- CDaoTableDef [MFC], CDaoTableDef
- CDaoTableDef [MFC], Append
- CDaoTableDef [MFC], CanUpdate
- CDaoTableDef [MFC], Close
- CDaoTableDef [MFC], Create
- CDaoTableDef [MFC], CreateField
- CDaoTableDef [MFC], CreateIndex
- CDaoTableDef [MFC], DeleteField
- CDaoTableDef [MFC], DeleteIndex
- CDaoTableDef [MFC], GetAttributes
- CDaoTableDef [MFC], GetConnect
- CDaoTableDef [MFC], GetDateCreated
- CDaoTableDef [MFC], GetDateLastUpdated
- CDaoTableDef [MFC], GetFieldCount
- CDaoTableDef [MFC], GetFieldInfo
- CDaoTableDef [MFC], GetIndexCount
- CDaoTableDef [MFC], GetIndexInfo
- CDaoTableDef [MFC], GetName
- CDaoTableDef [MFC], GetRecordCount
- CDaoTableDef [MFC], GetSourceTableName
- CDaoTableDef [MFC], GetValidationRule
- CDaoTableDef [MFC], GetValidationText
- CDaoTableDef [MFC], IsOpen
- CDaoTableDef [MFC], Open
- CDaoTableDef [MFC], RefreshLink
- CDaoTableDef [MFC], SetAttributes
- CDaoTableDef [MFC], SetConnect
- CDaoTableDef [MFC], SetName
- CDaoTableDef [MFC], SetSourceTableName
- CDaoTableDef [MFC], SetValidationRule
- CDaoTableDef [MFC], SetValidationText
- CDaoTableDef [MFC], m_pDAOTableDef
- CDaoTableDef [MFC], m_pDatabase
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
ms.openlocfilehash: adc31ccbf2be34aa1df1fa56111d1990701a6329
ms.sourcegitcommit: 7a6116e48c3c11b97371b8ae4ecc23adce1f092d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "81754687"
---
# <a name="cdaotabledef-class"></a>Класс CDaoTableDef

Представляет хранимое определение базовой или подключенной таблицы.

## <a name="syntax"></a>Синтаксис

```
class CDaoTableDef : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|Формирует объект `CDaoTableDef`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDaoTableDef::Приложение](#append)|Добавляет новую таблицу в базу данных.|
|[CDaoTableDef::CanUpdate](#canupdate)|Возвращает ненулевой, если таблица может быть обновлена (можно изменить определение полей или свойств таблицы).|
|[CDaoTableDef::Закрыть](#close)|Закрывает открытый стол.|
|[CDaoTableDef::Создание](#create)|Создает таблицу, которая может быть добавлена в базу данных с помощью [приложения.](#append)|
|[CDaoTableDef::CreateField](#createfield)|Вызывается для создания поля для таблицы.|
|[CDaoTableDef::CreateIndex](#createindex)|Вызывается для создания индекса для таблицы.|
|[CDaoTableDef::DeleteField](#deletefield)|Вызывается, чтобы удалить поле из таблицы.|
|[CDaoTableDef::DeleteIndex](#deleteindex)|Вызывается, чтобы удалить индекс из таблицы.|
|[CDaoTableDef::GetAttributes](#getattributes)|Возвращает значение, указывававое одну или несколько характеристик `CDaoTableDef` объекта.|
|[CDaoTableDef::GetConnect](#getconnect)|Возвращает значение, сокоторое где содержится информация об источнике таблицы.|
|[CDaoTableDef::GetDateCreated](#getdatecreated)|Возвращает дату и время создания базовой таблицы, лежащей в `CDaoTableDef` основе объекта.|
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|Возвращает дату и время последнего изменения, внесенного в дизайн базовой таблицы.|
|[CDaoTableDef::GetFieldCount](#getfieldcount)|Возвращает значение, представляющее количество полей в таблице.|
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|Возвращает конкретные виды информации о полях в таблице.|
|[CDaoTableDef::GetIndexCount](#getindexcount)|Возвращает количество индексов для таблицы.|
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|Возвращает конкретные виды информации об индексах для таблицы.|
|[CDaoTableDef::GetName](#getname)|Возвращает имя таблицы, определяемое пользователем.|
|[CDaoTableDefDef::GetRecordCount](#getrecordcount)|Возвращает количество записей в таблице.|
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|Возвращает значение, опознавававназвание прикрепленной таблицы в исходной базе данных.|
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|Возвращает значение, которое проверяет данные в поле по мере их изменения или добавления в таблицу.|
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Возвращает значение, определяемые текстом сообщения, отображается приложением, если значение объекта Field не соответствует указанному правилу проверки.|
|[CDaoTableDef::IsOpen](#isopen)|Возвращает ненулевой, если таблица открыта.|
|[CDaoTableDef::Открыто](#open)|Открывает существующую таблицу, хранящуюся в коллекции TableDef базы данных.|
|[CDaoTableDef::RefreshLink](#refreshlink)|Обновляет информацию о подключении для прилагаемой таблицы.|
|[CDaoTableDef::SetAttributes](#setattributes)|Устанавливает значение, указываводное одну или несколько характеристик `CDaoTableDef` объекта.|
|[CDaoTableDef::SetConnect](#setconnect)|Устанавливает значение, содеягакоторое источником таблицы.|
|[CDaoTableDef::SetName](#setname)|Устанавливает название таблицы.|
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|Устанавливает значение, опознававав название прилагаемой таблицы в исходной базе данных.|
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|Устанавливает значение, которое проверяет данные в поле по мере их изменения или добавления в таблицу.|
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Устанавливает значение, определяемые текстом сообщения, отображается приложением, если значение объекта Field не соответствует указанному правилу проверки.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|Указатель на интерфейс DAO, лежащий в основе объекта таблицы.|
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|Исходная база данных для этой таблицы.|

## <a name="remarks"></a>Remarks

Каждый объект базы данных DAO поддерживает коллекцию под названием TableDefs, которая содержит все сохраненные объекты таблицы DAO.

Вы манипулируете `CDaoTableDef` определением таблицы с помощью объекта. Например, администратор может сделать следующее:

- Изучите поле и структуру индекса любой локальной, присоединенной или внешней таблицы в базе данных.

- Вызов `SetConnect` и `SetSourceTableName` функции члена для прикрепленных `RefreshLink` таблиц и используйте функцию участника для обновления соединений на прилагаемые таблицы.

- Позвоните `CanUpdate` функции участника, чтобы определить, можно ли отображить определения поля в таблице.

- Получить или установить условия `GetValidationRule` `SetValidationRule`проверки `GetValidationText` с `SetValidationText` использованием и, и и и член функций.

- Используйте `Open` функцию участника для создания объекта типа таблицы, `CDaoRecordset` динасета или моментального типа.

    > [!NOTE]
    >  Классы баз данных DAO отличаются от классов баз данных MFC на основе open Database Connectivity (ODBC). Все названия классов баз данных DAO имеют префикс "CDao". Вы все еще можете получить доступ к источникам данных ODBC с классами DAO; Классы DAO обычно предлагают превосходные возможности, поскольку они специфичны для движка базы данных Microsoft Jet.

### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>Использовать объекты таблицы либо для работы с существующей таблицей, либо для создания новой таблицы

1. Во всех случаях сначала `CDaoTableDef` постройте объект, поставив указатель на объект [CDaoDatabase,](../../mfc/reference/cdaodatabase-class.md) к которому принадлежит таблица.

1. Затем сделайте следующее, в зависимости от того, что вы хотите:

   - Чтобы использовать существующую сохраненную таблицу, позвоните в функцию ["Открытая](#open) элемента объекта таблицы", предоставив имя сохраненной таблицы.

   - Чтобы создать новую таблицу, позвоните в функцию члена объекта [таблицы,](#create) поставляя название таблицы. Вызов [CreateField](#createfield) и [CreateIndex](#createindex) для добавления полей и индексов в таблицу.

   - Позвоните [в приложение,](#append) чтобы сохранить таблицу, приложив ее к коллекции TableDefs базы данных. `Create`помещает таблицу в открытое состояние, `Create` поэтому после `Open`звонка не звоните.

        > [!TIP]
        >  Самый простой способ создания сохраненных таблиц — создать их и хранить их в базе данных с помощью Microsoft Access. Затем вы можете открыть и использовать их в своем коде MFC.

Для использования объекта таблицы, который вы открыли `CDaoRecordset` или создали, создайте и откроете `dbOpenTable` объект, указав имя таблицы с значением в параметре *nOpenType.*

Чтобы использовать объект таблицы `CDaoRecordset` для создания объекта, вы обычно создаете или открываете таблицу, как описано выше, а затем создаете объект записи, передавая указатель объекту таблицы при вызове [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Таблица, которая вы проходите, должна находиться в открытом состоянии. Для получения дополнительной информации, см класс [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Когда вы закончите использовать объект таблицы, позвоните в функцию [члена Close;](../../mfc/reference/cdaorecordset-class.md#close) затем уничтожить объект таблицы.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDaoTableDef`

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

## <a name="cdaotabledefappend"></a><a name="append"></a>CDaoTableDef::Приложение

Вызов исчерпать эту функцию участника после вызова [Создать](#create) для создания нового объекта таблицы для сохранения таблицы в базе данных.

```
virtual void Append();
```

### <a name="remarks"></a>Remarks

Функция приспоняет объект к сбору TableDefs базы данных. Вы можете использовать таблицу в качестве временного объекта, определяя его, не применяя `Append`его, но если вы хотите сохранить и использовать его, вы должны позвонить.

> [!NOTE]
> Если вы попытаетесь прибовать неназванную таблицу (содержащую нулевые или пустые строки), MFC бросает исключение.

Для получения соответствующей информации, см.

## <a name="cdaotabledefcanupdate"></a><a name="canupdate"></a>CDaoTableDef::CanUpdate

Вызовите эту функцию участника, чтобы определить, можно ли изменить определение таблицы, лежащей в `CDaoTableDef` основе объекта.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, если структура таблицы (схема) может быть изменена (добавить или удалить поля и индексы), в противном случае 0.

### <a name="remarks"></a>Remarks

По умолчанию недавно созданная `CDaoTableDef` таблица, лежащая в основе объекта, может быть обновлена, а прилагаемая таблица, лежащая в `CDaoTableDef` основе объекта, не может быть обновлена. Объект `CDaoTableDef` может быть updatable, даже если полученный рекордет не updatable.

Для получения соответствующей информации смотрите тему "Updatable Property" в справке DAO.

## <a name="cdaotabledefcdaotabledef"></a><a name="cdaotabledef"></a>CDaoTableDef::CDaoTableDef

Формирует объект `CDaoTableDef`.

```
CDaoTableDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Параметры

*pDatabase*<br/>
Указатель на объект [CDaoDatabase.](../../mfc/reference/cdaodatabase-class.md)

### <a name="remarks"></a>Remarks

После построения объекта необходимо вызвать функцию [«Создание»](#create) или [«Открыть](#open) объект». Когда вы закончите с объектом, вы должны `CDaoTableDef` вызвать его функцию [Закрыть](#close) и уничтожить объект.

## <a name="cdaotabledefclose"></a><a name="close"></a>CDaoTableDef::Закрыть

Вызовите эту функцию участника, чтобы закрыть и освободить объект таблицы def.

```
virtual void Close();
```

### <a name="remarks"></a>Remarks

Обычно после `Close`вызова вы удаляете объект таблицы, если он был выделен **новым**.

Вы можете [Open](#open) позвонить `Close`открыть еще раз после вызова . Это позволяет повторно использовать объект таблицы.

Для получения соответствующей информации смотрите тему "Закрыть метод" в справке DAO.

## <a name="cdaotabledefcreate"></a><a name="create"></a>CDaoTableDef::Создание

Вызовите эту функцию участника для создания новой сохраненной таблицы.

```
virtual void Create(
    LPCTSTR lpszName,
    long lAttributes = 0,
    LPCTSTR lpszSrcTable = NULL,
    LPCTSTR lpszConnect = NULL);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строку, содержащую название таблицы.

*lАтрибуты*<br/>
Значение, соответствующее характеристикам таблицы, представленной объектом таблицы. Вы можете использовать bitwise-OR для объединения любой из следующих констант:

|Константа|Описание|
|--------------|-----------------|
|`dbAttachExclusive`|Для баз данных, которые используют движок базы данных Microsoft Jet, указывается, что таблица является прилагаемой таблицей, открытой для исключительного использования.|
|`dbAttachSavePWD`|Для баз данных, которые используют движок базы данных Microsoft Jet, указывается, что идентификатор пользователя и пароль для прилагаемой таблицы сохраняются с информацией о подключении.|
|`dbSystemObject`|Указывает, что таблица представляет собой системную таблицу, предоставляемую движком базы данных Microsoft Jet.|
|`dbHiddenObject`|Указывает, что таблица представляет собой скрытую таблицу, предоставленную движком базы данных Microsoft Jet.|

*lpszSrcTable*<br/>
Указатель на строку, содержащую имя исходной таблицы. По умолчанию это значение инициализировано как NULL.

*lpszConnect*<br/>
Указатель на строку, содержащую строку соединения по умолчанию. По умолчанию это значение инициализировано как NULL.

### <a name="remarks"></a>Remarks

После того как вы назвали таблицу, вы можете вызвать [приложение,](#append) чтобы сохранить таблицу в коллекции TableDefs базы данных. После `Append`вызова таблица находится в открытом состоянии, и вы можете использовать его для создания объекта [CDaoRecordset.](../../mfc/reference/cdaorecordset-class.md)

Для получения соответствующей информации смотрите тему "Создание метода создания таблицы" в справке DAO.

## <a name="cdaotabledefcreatefield"></a><a name="createfield"></a>CDaoTableDef::CreateField

Вызовите эту функцию участника, чтобы добавить поле в таблицу.

```cpp
void CreateField(
    LPCTSTR lpszName,
    short nType,
    long lSize,
    long lAttributes = 0);

void CreateField(CDaoFieldInfo& fieldinfo);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на выражение строки, определяющее имя этого поля.

*nType*<br/>
Значение, указывающее тип данных поля. Параметр может быть одним из следующих значений:

|Тип|Размер (в байтах)|Описание|
|----------|--------------------|-----------------|
|`dbBoolean`|1 байт|BOOL|
|`dbByte`|BYTE|
|`dbInteger`|2|INT|
|`dbLong`|4|long|
|`dbCurrency`|8|Валюта [(COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|FLOAT|
|`dbDouble`|8|double|
|`dbDate`|8|Дата/время [(COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Текст ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Длинные двоичные (OLE объект), [CLongBinary](../../mfc/reference/clongbinary-class.md) или [CByteArray](../../mfc/reference/cbytearray-class.md)|
|`dbMemo`|0|Памятка ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|

*lРазмер*<br/>
Значение, указывавщее максимальный размер в байтах поля, содержащего текст, или фиксированный размер поля, содержащего текстовые или числовые значения. Параметр *lSize* игнорируется для всех, кроме текстовых полей.

*lАтрибуты*<br/>
Значение, соответствующее характеристикам поля, и которое может быть объединено с помощью bitwise-OR.

|Константа|Описание|
|--------------|-----------------|
|`dbFixedField`|Размер поля фиксируется (по умолчанию для численных полей).|
|`dbVariableField`|Размер поля является переменным (только текстовые поля).|
|`dbAutoIncrField`|Значение поля для новых записей автоматически приравнивается к уникальному длинному целыку, который нельзя изменить. Поддерживается только для таблиц баз данных Microsoft Jet.|
|`dbUpdatableField`|Значение поля может быть изменено.|
|`dbDescending`|Поле сортируется по нисходящей (я - A или 100 - 0) (применяется только к объекту поля в коллекции Полей объекта Индекса). Если вы опустите эту константу, поле сортируется в восходящем порядке (A - No или 0 - 100) (по умолчанию).|

*Fieldinfo*<br/>
Ссылка на структуру [CDaoFieldInfo.](../../mfc/reference/cdaofieldinfo-structure.md)

### <a name="remarks"></a>Remarks

Объект `DAOField` A (OLE) создается и пригоден `DAOTableDef` к коллекции Полей (OLE) объекта. Помимо использования для изучения свойств объектов, можно также использовать `CDaoFieldInfo` для построения вхнужного параметра для создания новых полей в таблице. Первая версия `CreateField` проще в использовании, но если вы хотите более тонкого управления, вы можете использовать вторую версию `CreateField`, которая принимает `CDaoFieldInfo` параметр.

Если вы используете `CreateField` версию, которая занимает `CDaoFieldInfo` параметр, вы должны `CDaoFieldInfo` тщательно установить каждый из следующих членов структуры:

- `m_strName`

- `m_nType`

- `m_lSize`

- `m_lAttributes`

- `m_bAllowZeroLength`

Остальные члены `CDaoFieldInfo` должны быть установлены на **0**, FALSE, или пустой `CDaoException` строки, в соответствии с соответствующими для члена, или может произойти.

Для получения соответствующей информации смотрите тему "Создатьметод" в справке DAO.

## <a name="cdaotabledefcreateindex"></a><a name="createindex"></a>CDaoTableDef::CreateIndex

Вызовите эту функцию, чтобы добавить индекс в таблицу.

```cpp
void CreateIndex(CDaoIndexInfo& indexinfo);
```

### <a name="parameters"></a>Параметры

*индексинфо*<br/>
Ссылка на структуру [CDaoIndexInfo.](../../mfc/reference/cdaoindexinfo-structure.md)

### <a name="remarks"></a>Remarks

Индексы определяют порядок записей, доступ к которых осуществляется из таблиц баз данных, и принимаются ли дублирующиеся записи. Индексы также обеспечивают эффективный доступ к данным.

Не нужно создавать индексы для таблиц, но в больших, неиндексированных таблицах доступ к определенной записи или создание набора записей может занять много времени. С другой стороны, создание слишком большого количества индексов замедляет обновление, приложение и удаление операций, поскольку все индексы автоматически обновляются. Учитывайте эти факторы при том, какие индексы создавать.

Следующие члены `CDaoIndexInfo` структуры должны быть установлены:

- `m_strName`Имя должно быть предоставлено.

- `m_pFieldInfos`Должен указывать на `CDaoIndexFieldInfo` массив структур.

- `m_nFields`Необходимо указать количество полей `CDaoFieldInfo` в массиве структур.

Остальные участники будут проигнорированы, если они будут установлены на FALSE. Кроме того, `m_lDistinctCount` участник игнорируется при создании индекса.

## <a name="cdaotabledefdeletefield"></a><a name="deletefield"></a>CDaoTableDef::DeleteField

Вызов ифункции этого участника, чтобы удалить поле и сделать его недоступным.

```cpp
void DeleteField(LPCTSTR lpszName);
void DeleteField(int nIndex);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на выражение строки, которое является именем существующего поля.

*Nindex*<br/>
Индекс поля в коллекции полей с нулевым уровнем, для поиска по индексу.

### <a name="remarks"></a>Remarks

Эту функцию участника можно использовать на новом объекте, который не был приложен к базе данных или когда [CanUpdate](#canupdate) возвращается ненулево.

Для получения соответствующей информации смотрите тему "Метод удаления" в справке DAO.

## <a name="cdaotabledefdeleteindex"></a><a name="deleteindex"></a>CDaoTableDef::DeleteIndex

Вызовите эту функцию участника, чтобы удалить индекс в основной таблице.

```cpp
void DeleteIndex(LPCTSTR lpszName);
void DeleteIndex(int nIndex);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на выражение строки, которое является именем существующего индекса.

*Nindex*<br/>
Индекс массива объекта индекса в нулевой коллекции TableDefs базы данных для поиска по индексу.

### <a name="remarks"></a>Remarks

Эту функцию участника можно использовать на новом объекте, который не был приложен к базе данных или когда [CanUpdate](#canupdate) возвращается ненулево.

Для получения соответствующей информации смотрите тему "Метод удаления" в справке DAO.

## <a name="cdaotabledefgetattributes"></a><a name="getattributes"></a>CDaoTableDef::GetAttributes

Для `CDaoTableDef` объекта значение возврата определяет характеристики таблицы, представленной `CDaoTableDef` объектом, и может быть суммой этих констант:

```
long GetAttributes();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, указывававое одну или несколько характеристик `CDaoTableDef` объекта.

### <a name="remarks"></a>Remarks

|Константа|Описание|
|--------------|-----------------|
|`dbAttachExclusive`|Для баз данных, которые используют движок базы данных Microsoft Jet, указывается, что таблица является прилагаемой таблицей, открытой для исключительного использования.|
|`dbAttachSavePWD`|Для баз данных, которые используют движок базы данных Microsoft Jet, указывается, что идентификатор пользователя и пароль для прилагаемой таблицы сохраняются с информацией о подключении.|
|`dbSystemObject`|Указывает, что таблица представляет собой системную таблицу, предоставляемую движком базы данных Microsoft Jet.|
|`dbHiddenObject`|Указывает, что таблица представляет собой скрытую таблицу, предоставленную движком базы данных Microsoft Jet.|
|`dbAttachedTable`|Указывает, что таблица является прилагаемой таблицей из базы данных, не относясь к ODBC, например, к базе данных Paradox.|
|`dbAttachedODBC`|Указывает, что таблица — это прилагаемая таблица из базы данных ODBC, например, Microsoft S'L Server.|

Таблица систем — это таблица, созданная движком базы данных Microsoft Jet для хранения различной внутренней информации.

Скрытая таблица — это таблица, созданная для временного использования движком базы данных Microsoft Jet.

Для получения соответствующей информации смотрите тему "Свойства свойств" в справке DAO.

## <a name="cdaotabledefgetconnect"></a><a name="getconnect"></a>CDaoTableDef::GetConnect

Вызовите эту функцию участника, чтобы получить строку соединения для источника данных.

```
CString GetConnect();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CString` содержащий путь и тип базы данных для таблицы.

### <a name="remarks"></a>Remarks

Для `CDaoTableDef` объекта, представляющего прилагаемую таблицу, `CString` объект состоит из одной или двух частей (спекулянт типа базы данных и путь к базе данных).

Путь, указанный в таблице ниже, представляет собой полный путь для каталога, содержащего файлы базы данных, и должен предшествовать идентификатору "DATABASE". В некоторых случаях (как в случае с базами данных Microsoft Jet и Microsoft Excel) в аргумент пути базы данных включено определенное имя файла.

Таблица в [CDaoTableDef::SetConnect](#setconnect) показывает возможные типы баз данных и соответствующие специфики базы данных и пути:

Для базовых таблиц баз данных Microsoft Jet спецификация является пустой строкой ("").

Если пароль необходим, но не предоставлен, драйвер ODBC отображает поле для диалога входа при первом доступе к таблице и снова, если соединение закрыто и возобновлено. Если прилагаемая `dbAttachSavePWD` таблица имеет атрибут, запрос входа не будет отображаться при повторном открытии таблицы.

Для получения соответствующей информации смотрите тему "Подключение собственности" в справке DAO.

## <a name="cdaotabledefgetdatecreated"></a><a name="getdatecreated"></a>CDaoTableDef::GetDateCreated

Вызов ими функции для определения даты `CDaoTableDef` и времени создания таблицы, лежащей в основе объекта.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащее дату и время создания таблицы, лежащей в `CDaoTableDef` основе объекта.

### <a name="remarks"></a>Remarks

Настройки даты и времени получены из компьютера, на котором была создана базовая таблица или последнее обновление. В многопользовательской среде пользователи должны получать эти настройки непосредственно с файлового сервера, чтобы избежать расхождений; то есть, все клиенты должны использовать "стандартный" источник времени - возможно, с одного сервера.

Для получения соответствующей информации, см.

## <a name="cdaotabledefgetdatelastupdated"></a><a name="getdatelastupdated"></a>CDaoTableDef::GetDateLastUpdated

Вызов ими функции для определения даты `CDaoTableDef` и времени последнего обновления таблицы, лежащей в основе объекта.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащее дату и время `CDaoTableDef` последнего обновления таблицы, лежащей в основе объекта.

### <a name="remarks"></a>Remarks

Настройки даты и времени получены из компьютера, на котором была создана базовая таблица или последнее обновление. В многопользовательской среде пользователи должны получать эти настройки непосредственно с файлового сервера, чтобы избежать расхождений; то есть, все клиенты должны использовать "стандартный" источник времени - возможно, с одного сервера.

Для получения соответствующей информации, см.

## <a name="cdaotabledefgetfieldcount"></a><a name="getfieldcount"></a>CDaoTableDef::GetFieldCount

Вызовите эту функцию участника, чтобы получить количество полей, определенных в таблице.

```
short GetFieldCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество полей в таблице.

### <a name="remarks"></a>Remarks

Если его значение составляет 0, в коллекции нет объектов.

Для получения соответствующей информации, см.

## <a name="cdaotabledefgetfieldinfo"></a><a name="getfieldinfo"></a>CDaoTableDef::GetFieldInfo

Вызовите эту функцию участника для получения различного рода информации о поле, определенном в таблице.

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
Индекс объекта поля в коллекции полей с нулевым уровнем, для поиска по индексу.

*Fieldinfo*<br/>
Ссылка на структуру [CDaoFieldInfo.](../../mfc/reference/cdaofieldinfo-structure.md)

*dwInfoOptions*<br/>
Параметры, которые определяют, какую информацию о поле для извлечения. Доступные варианты перечислены здесь вместе с тем, что они вызывают функцию возвращения:

- `AFX_DAO_PRIMARY_INFO`(По умолчанию) Имя, тип, размер, атрибуты. Используйте эту опцию для быстрой производительности.

- `AFX_DAO_SECONDARY_INFO`Первичная информация, плюс: Обыденное положение, Обязательно, Разрешить нулевую длину, Коллажирование заказа, Иностранное имя, Поле источника, Таблица источника

- `AFX_DAO_ALL_INFO`Первичная и второстепенная информация, а также: Правило валидации, Текст валидации, Значение по умолчанию

*lpszName*<br/>
Указатель на название объекта поля, для поиска по имени. Название представляет собой строку с до 64 символов, которые однозначно имена поля.

### <a name="remarks"></a>Remarks

Одна из версий функции позволяет искать поле по индексу. Другая версия позволяет искать поле по имени.

Для описания возвращенной информации [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) см. Эта структура имеет членов, которые соответствуют пунктам информации, перечисленных выше в описании *dwInfoOptions*. Когда вы запрашиваете информацию на одном уровне, вы получаете информацию для любых предыдущих уровней, а также.

Для получения соответствующей информации смотрите тему "Свойства свойств" в справке DAO.

## <a name="cdaotabledefgetindexcount"></a><a name="getindexcount"></a>CDaoTableDef::GetIndexCount

Вызовите эту функцию участника, чтобы получить количество индексов для таблицы.

```
short GetIndexCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество индексов для таблицы.

### <a name="remarks"></a>Remarks

Если его значение составляет 0, в коллекции нет индексов.

Для получения соответствующей информации, см.

## <a name="cdaotabledefgetindexinfo"></a><a name="getindexinfo"></a>CDaoTableDef::GetIndexInfo

Вызовите эту функцию участника для получения различного рода информации об индексе, определенном в таблице.

```cpp
void GetIndexInfo(
    int nIndex,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

void GetIndexInfo(
    LPCTSTR lpszName,
    CDaoIndexInfo& indexinfo,
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```

### <a name="parameters"></a>Параметры

*Nindex*<br/>
Числовый индекс объекта Индекса в коллекции индексов с нулевым уровнем таблицы для поиска по его положению в коллекции.

*индексинфо*<br/>
Ссылка на структуру [CDaoIndexInfo.](../../mfc/reference/cdaoindexinfo-structure.md)

*dwInfoOptions*<br/>
Параметры, которые определяют, какую информацию об индексе для извлечения. Доступные варианты перечислены здесь вместе с тем, что они вызывают функцию возвращения:

- `AFX_DAO_PRIMARY_INFO`Имя, Полевая информация, Поля. Используйте эту опцию для быстрой производительности.

- `AFX_DAO_SECONDARY_INFO`Первичная информация, а также: Первичная, Уникальная, Кластерная, Игнорируемые Нулы, Необходимые, Иностранные

- `AFX_DAO_ALL_INFO`Первичная и второстепенная информация, плюс: Отдельный граф

*lpszName*<br/>
Указатель на имя объекта индекса для поиска по имени.

### <a name="remarks"></a>Remarks

Одна из версий функции позволяет искать индекс по его положению в коллекции. Другая версия позволяет искать индекс по имени.

Для описания возвращенной информации [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) см. Эта структура имеет членов, которые соответствуют пунктам информации, перечисленных выше в описании *dwInfoOptions*. Когда вы запрашиваете информацию на одном уровне, вы получаете информацию для любых предыдущих уровней, а также.

Для получения соответствующей информации смотрите тему "Свойства свойств" в справке DAO.

## <a name="cdaotabledefgetname"></a><a name="getname"></a>CDaoTableDef::GetName

Вызовите эту функцию участника, чтобы получить определенное пользователем имя основной таблицы.

```
CString GetName();
```

### <a name="return-value"></a>Возвращаемое значение

Имя, определенное пользователем для таблицы.

### <a name="remarks"></a>Remarks

Это имя начинается с буквы и может содержать максимум 64 символов. Он может включать числа и подчеркивать символы, но не может включать знаки препинания или пробелы.

Для получения соответствующей информации, см.

## <a name="cdaotabledefgetrecordcount"></a><a name="getrecordcount"></a>CDaoTableDefDef::GetRecordCount

Позвоните в эту функцию участника, `CDaoTableDef` чтобы узнать, сколько записей в объекте.

```
long GetRecordCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество записей, доступных в объекте таблицы.

### <a name="remarks"></a>Remarks

Вызов `GetRecordCount` объекта типа `CDaoTableDef` таблицы отражает приблизительное количество записей в таблице и сразу же затрагивается при добавлении и удалении записей таблицы. Откатные транзакции будут отображаться как часть количества записей, пока вы не позвоните [cDaoWorkSpace::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase). Объект `CDaoTableDef` без записей имеет значение значения подсчета записей 0. При работе с прикрепленными таблицами `GetRecordCount` или базами данных ODBC всегда возвращается -1.

Для получения соответствующей информации смотрите тему "RecordCount Property" в справке DAO.

## <a name="cdaotabledefgetsourcetablename"></a><a name="getsourcetablename"></a>CDaoTableDef::GetSourceTableName

Вызовите эту функцию участника, чтобы получить имя прилагаемой таблицы в исходной базе данных.

```
CString GetSourceTableName();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CString` опознавающее исходное имя прилагаемой таблицы, или пустую строку, если родная таблица данных.

### <a name="remarks"></a>Remarks

Прилагаемая таблица — это таблица в другой базе данных, связанная с базой данных Microsoft Jet. Данные для прикрепленных таблиц остаются во внешней базе данных, где ими могут манипулировать другие приложения.

Для получения соответствующей информации, см.

## <a name="cdaotabledefgetvalidationrule"></a><a name="getvalidationrule"></a>CDaoTableDef::GetValidationRule

Вызовите эту функцию участника, чтобы получить правило проверки для таблицы.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CString` проверяемый данными в поле при изменении или добавлении в таблицу.

### <a name="remarks"></a>Remarks

Правила проверки используются в связи с операциями обновления. Если таблица содержит правило проверки, обновления в таблице должны соответствовать заранее определенным критериям до изменения данных. Если изменение не соответствует критериям, выбрасывается исключение, содержащее значение [GetValidationText.](#getvalidationtext) Для `CDaoTableDef` объекта это `CString` только для прилагаемой таблицы и чтение/запись для базовой таблицы.

Для получения соответствующей информации, см.

## <a name="cdaotabledefgetvalidationtext"></a><a name="getvalidationtext"></a>CDaoTableDef::GetValidationText

Вызов ими функции для извлечения строки для отображения при вводе пользователем данных, не совпадает с правилом проверки.

```
CString GetValidationText();
```

### <a name="return-value"></a>Возвращаемое значение

Объект, `CString` описанный текст, если пользователь вводит данные, не совпадающие с правилом проверки.

### <a name="remarks"></a>Remarks

Для `CDaoTableDef` объекта это `CString` только для прилагаемой таблицы и чтение/запись для базовой таблицы.

Для получения соответствующей информации смотрите тему "ValidationText Property" в справке DAO.

## <a name="cdaotabledefisopen"></a><a name="isopen"></a>CDaoTableDef::IsOpen

Вызовите эту функцию `CDaoTableDef` участника, чтобы определить, открыт ли объект в настоящее время.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Возвращаемое значение

Nonzero, `CDaoTableDef` если объект открыт; в противном случае 0.

### <a name="remarks"></a>Remarks

## <a name="cdaotabledefm_pdatabase"></a><a name="m_pdatabase"></a>CDaoTableDef::m_pDatabase

Содержит указатель на объект [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) для этой таблицы.

### <a name="remarks"></a>Remarks

## <a name="cdaotabledefm_pdaotabledef"></a><a name="m_pdaotabledef"></a>CDaoTableDef::m_pDAOTableDef

Содержит указатель на интерфейс OLE для объекта dAO `CDaoTableDef` tabledef, лежащего в основе объекта.

### <a name="remarks"></a>Remarks

Используйте этот указатель, если вам нужно получить доступ к интерфейсу DAO напрямую.

## <a name="cdaotabledefopen"></a><a name="open"></a>CDaoTableDef::Открыто

Вызовите эту функцию участника, чтобы открыть таблицу, ранее сохраненную в коллекции TableDef.

```
virtual void Open(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строку, опознавательную имя таблицы.

### <a name="remarks"></a>Remarks

## <a name="cdaotabledefrefreshlink"></a><a name="refreshlink"></a>CDaoTableDef::RefreshLink

Вызовите эту функцию участника, чтобы обновить информацию о подключении к прилагаемой таблице.

```cpp
void RefreshLink();
```

### <a name="remarks"></a>Remarks

Вы меняете информацию о подключении к прилагаемой таблице, вызывая [SetConnect](#setconnect) на соответствующий `CDaoTableDef` объект, а затем используя функцию `RefreshLink` участника для обновления информации. При вызове `RefreshLink`свойства прикрепленной таблицы не изменяются.

Чтобы заставить измененную информацию о подключении вступить в силу, все открытые объекты [CDaoRecordset,](../../mfc/reference/cdaorecordset-class.md) основанные на этом таблице, должны быть закрыты.

Для получения соответствующей информации, см.

## <a name="cdaotabledefsetattributes"></a><a name="setattributes"></a>CDaoTableDef::SetAttributes

Устанавливает значение, указываводное одну или несколько характеристик `CDaoTableDef` объекта.

```cpp
void SetAttributes(long lAttributes);
```

### <a name="parameters"></a>Параметры

*lАтрибуты*<br/>
Характеристики таблицы представлены `CDaoTableDef` объектом и могут быть суммой этих констант:

|Константа|Описание|
|--------------|-----------------|
|`dbAttachExclusive`|Для баз данных, которые используют движок базы данных Microsoft Jet, указывается, что таблица является прилагаемой таблицей, открытой для исключительного использования.|
|`dbAttachSavePWD`|Для баз данных, которые используют движок базы данных Microsoft Jet, указывается, что идентификатор пользователя и пароль для прилагаемой таблицы сохраняются с информацией о подключении.|
|`dbSystemObject`|Указывает, что таблица представляет собой системную таблицу, предоставляемую движком базы данных Microsoft Jet.|
|`dbHiddenObject`|Указывает, что таблица представляет собой скрытую таблицу, предоставленную движком базы данных Microsoft Jet.|

### <a name="remarks"></a>Remarks

При настройке нескольких атрибутов, вы можете объединить их, суммируя соответствующие константы с помощью оператора bitwise-OR. Установка `dbAttachExclusive` на непривязанную таблицу создает исключение. Объединение следующих значений также приводит к исключению:

- **dbAttachExclusive &#124; dbAttachedODBC**

- **dbAttachSavePWD &#124; dbAttachedTable**

Для получения соответствующей информации смотрите тему "Свойства свойств" в справке DAO.

## <a name="cdaotabledefsetconnect"></a><a name="setconnect"></a>CDaoTableDef::SetConnect

Для `CDaoTableDef` объекта, представляющего прилагаемую таблицу, объект строки состоит из одной или двух частей (разоспектитель типа базы данных и путь к базе данных).

```cpp
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Параметры

*lpszConnect*<br/>
Указатель на выражение строки, которое определяет дополнительные параметры для передачи в ODBC или устанавливаемые драйверы ISAM.

### <a name="remarks"></a>Remarks

Путь, указанный в таблице ниже, представляет собой полный путь для каталога, содержащего файлы базы данных, и должен предшествовать идентификатору "DATABASE". В некоторых случаях (как в случае с базами данных Microsoft Jet и Microsoft Excel) в аргумент пути базы данных включено определенное имя файла.

> [!NOTE]
> Не включайте белое пространство вокруг равного знака в\\операторы пути формы "DATABASE-drive: "путь". Это приведет к тому, что исключение будет брошено, а соединение сбой.

В следующей таблице показаны возможные типы баз данных и соответствующие ими спецификаторы и пути баз данных:

|Тип базы данных|Описатель|путь|
|-------------------|---------------|----------|
|База данных с использованием движка базы данных Jet|"[ `database`];"|" `drive`\\\ :*имя файла**пути*\\\ . MDB"|
|dBASE III|"dBASE III;"|" `drive`\\\ :*путь*"|
|dBASE IV|"dBASE IV;"|" `drive`\\\ :*путь*"|
|dBASE 5|"dBASE 5.0;"|" `drive`\\\ :*путь*"|
|Парадокс 3.x|"Парадокс 3.x;"|" `drive`\\\ :*путь*"|
|Парадокс 4.x|"Парадокс 4.x;"|" `drive`\\\ :*путь*"|
|Парадокс 5.x|"Парадокс 5.x;"|" `drive`\\\ :*путь*"|
|Excel 3.0|"Excel 3.0;"|" `drive`\\\ :*имя файла**пути*\\\ . XLS"|
|Excel 4.0|"Excel 4.0;"|" `drive`\\\ :*имя файла**пути*\\\ . XLS"|
|Excel 5.0 или Excel 95|"Excel 5.0;"|" `drive`\\\ :*имя файла**пути*\\\ . XLS"|
|Excel 97|"Excel 8.0;"|" `drive`\\\ :*имя файла**пути*\ . XLS"|
|HTML Импорт|"HTML Импорт;"|" `drive`\\\ :*имя файла**пути*\ "|
|Html Экспорт|"HTML Экспорт;"|" `drive`\\\ :*путь*"|
|текст|"Текст;"|"драйв:\\"путь"|
|ODBC|"ODBC; БАЗИС; `database` *Пользователь*UID ; *Пароль*PWD; DSN' *имя источника данных;* LOGINTIMEOUT *секунд;*" (Это не может быть полной строки соединения для всех серверов; это всего лишь пример. Очень важно не иметь пробелов между параметрами.)|None|
|Exchange|"Обмен;<br /><br /> ПАПКА MAPILEVEL; *folderpath*<br /><br /> «TABLETYPE» 0 &#124; 1<br /><br /> Профиль *«PROFILE»*;»<br /><br /> Пароль «PWD»; *password*<br /><br /> (DATABASE) `database`;»|*"драйв*\\\ :*имя файла**пути*\\\ . MDB"|

> [!NOTE]
> Btrieve больше не поддерживается по состоянию на DAO 3.5.

Вы должны использовать двойной\\\\backslash ( ) в строках соединения. Если вы изменили свойства существующего `SetConnect`соединения с помощью, вы должны впоследствии позвонить [в RefreshLink.](#refreshlink) Если вы инициализируете свойства подключения с использованием, `SetConnect`вам не нужно звонить, `RefreshLink`но если вы решите сделать это, сначала прибвывайте таблицу.

Если пароль необходим, но не предоставлен, драйвер ODBC отображает поле для диалога входа при первом доступе к таблице и снова, если соединение закрыто и возобновлено.

Можно установить строку `CDaoTableDef` соединения для объекта, предоставив исходный аргумент функции `Create` члена. Вы можете проверить настройки, чтобы определить тип, путь, идентификатор пользователя, пароль или источник данных ODBC базы данных. Для получения дополнительной информации ознакомьтесь с документацией для конкретного драйвера.

Для получения соответствующей информации смотрите тему "Подключение собственности" в справке DAO.

## <a name="cdaotabledefsetname"></a><a name="setname"></a>CDaoTableDef::SetName

Вызовите эту функцию участника, чтобы установить имя, определяемое пользователем, для таблицы.

```cpp
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на выражение строки, опознавававав имя для таблицы.

### <a name="remarks"></a>Remarks

Имя должно начинаться с буквы и может содержать не более 64 символов. Он может включать числа и подчеркивать символы, но не может включать знаки препинания или пробелы.

Для получения соответствующей информации, см.

## <a name="cdaotabledefsetsourcetablename"></a><a name="setsourcetablename"></a>CDaoTableDef::SetSourceTableName

Вызовите эту функцию участника, чтобы указать имя прилагаемой `CDaoTableDef` таблицы или имя базовой таблицы, на которой основан объект, поскольку оно существует в исходном источнике данных.

```cpp
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```

### <a name="parameters"></a>Параметры

*lpszSrcTableName*<br/>
Указатель на выражение строки, опознавававав имя таблицы во внешней базе данных. Для базовой таблицы настройка представляет собой пустую строку ("").

### <a name="remarks"></a>Remarks

Затем необходимо позвонить [в RefreshLink](#refreshlink). Эта настройка свойства пуста для базовой таблицы и читает/записывает для прикрепленной таблицы или объекта, не прилагаемого к коллекции.

Для получения соответствующей информации, см.

## <a name="cdaotabledefsetvalidationrule"></a><a name="setvalidationrule"></a>CDaoTableDef::SetValidationRule

Вызовите эту функцию участника, чтобы установить правило проверки для таблицы.

```cpp
void SetValidationRule(LPCTSTR lpszValidationRule);
```

### <a name="parameters"></a>Параметры

*lpszValidationПравило*<br/>
Указатель на выражение строки, проверящее операцию.

### <a name="remarks"></a>Remarks

Правила проверки используются в связи с операциями обновления. Если таблица содержит правило проверки, обновления в таблице должны соответствовать заранее определенным критериям до изменения данных. Если изменение не соответствует критериям, отображается исключение, содержащее текст [GetValidationText.](#getvalidationtext)

Проверка поддерживается только для баз данных, которые используют движок базы данных Microsoft Jet. Выражение не может относиться к функциям, определенным пользователям, агрегированным функциям домена, агрегированным функциям s'L или запросам. Правило проверки `CDaoTableDef` объекта может относиться к нескольким полям в этом объекте.

Например, для полей, названных *hire_date* и *termination_date*правило проверки может быть:

[!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]

Для получения соответствующей информации, см.

## <a name="cdaotabledefsetvalidationtext"></a><a name="setvalidationtext"></a>CDaoTableDef::SetValidationText

Вызовите эту функцию участника, чтобы установить `CDaoTableDef` текст исключения правила проверки для объекта с базовой таблицей, поддерживаемой движком базы данных Microsoft Jet.

```cpp
void SetValidationText(LPCTSTR lpszValidationText);
```

### <a name="parameters"></a>Параметры

*lpszValidationТекст*<br/>
Указатель на строку выражения, которое определяет текст отображается, если введенные данные недействительны.

### <a name="remarks"></a>Remarks

Нельзя устанавливать текст проверки прикрепленной таблицы.

Для получения соответствующей информации смотрите тему "ValidationText Property" в справке DAO.

## <a name="see-also"></a>См. также раздел

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[CDaoDatabase Класс](../../mfc/reference/cdaodatabase-class.md)<br/>
[CDaoRecordset класс](../../mfc/reference/cdaorecordset-class.md)
