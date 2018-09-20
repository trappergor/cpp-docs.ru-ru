---
title: Класс CDaoTableDef | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f678a00d4556cf81ad378088df2525038bbdd6a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46426371"
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
|[CDaoTableDef::CDaoTableDef](#cdaotabledef)|Создает объект `CDaoTableDef`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CDaoTableDef::Append](#append)|Добавляет новую таблицу в базу данных.|
|[CDaoTableDef::CanUpdate](#canupdate)|Возвращает ненулевое значение, если можно обновить таблицу (можно изменить определение полей или свойств таблицы).|
|[CDaoTableDef::Close](#close)|Закрывает открытые tabledef.|
|[CDaoTableDef::Create](#create)|Создает таблицу, которую можно добавить базу данных с помощью [Append](#append).|
|[CDaoTableDef::CreateField](#createfield)|Вызывается, чтобы создать поле для таблицы.|
|[CDaoTableDef::CreateIndex](#createindex)|Вызывается, чтобы создать индекс для таблицы.|
|[CDaoTableDef::DeleteField](#deletefield)|Вызывается, чтобы удалить поле из таблицы.|
|[CDaoTableDef::DeleteIndex](#deleteindex)|Вызывается для удаления индекса из таблицы.|
|[CDaoTableDef::GetAttributes](#getattributes)|Возвращает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.|
|[CDaoTableDef::GetConnect](#getconnect)|Возвращает значение, предоставляющее сведения об источнике таблицы.|
|[CDaoTableDef::GetDateCreated](#getdatecreated)|Возвращает дату и время в базовой таблице базовый `CDaoTableDef` был создан объект.|
|[CDaoTableDef::GetDateLastUpdated](#getdatelastupdated)|Возвращает дату и время последнего изменения структуры базовой таблицы.|
|[CDaoTableDef::GetFieldCount](#getfieldcount)|Возвращает значение, представляющее количество полей в таблице.|
|[CDaoTableDef::GetFieldInfo](#getfieldinfo)|Возвращает сведения о полях определенных типов в таблице.|
|[CDaoTableDef::GetIndexCount](#getindexcount)|Возвращает число индексов для таблицы.|
|[CDaoTableDef::GetIndexInfo](#getindexinfo)|Возвращает определенные виды информации о индексы для таблицы.|
|[CDaoTableDef::GetName](#getname)|Возвращает имя пользовательской таблицы.|
|[CDaoTableDef::GetRecordCount](#getrecordcount)|Возвращает число записей в таблице.|
|[CDaoTableDef::GetSourceTableName](#getsourcetablename)|Возвращает значение, указывающее имя подключенной таблицы базы данных-источника.|
|[CDaoTableDef::GetValidationRule](#getvalidationrule)|Возвращает значение, которое проверяет данные в поля, как его изменить или добавить в таблицу.|
|[CDaoTableDef::GetValidationText](#getvalidationtext)|Возвращает значение, указывающее текст сообщения, которое отображает приложения, если значение объекта полей не удовлетворяет указанное правило проверки.|
|[CDaoTableDef::IsOpen](#isopen)|Возвращает ненулевое значение, если таблица является откройте.|
|[CDaoTableDef::Open](#open)|Открывает существующий tabledef, хранящиеся в базе данных, TableDef элемента коллекции.|
|[CDaoTableDef::RefreshLink](#refreshlink)|Обновляет сведения о соединении для подключенной таблицы.|
|[CDaoTableDef::SetAttributes](#setattributes)|Задает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.|
|[CDaoTableDef::SetConnect](#setconnect)|Задает значение, предоставляющее сведения об источнике таблицы.|
|[CDaoTableDef::SetName](#setname)|Задает имя таблицы.|
|[CDaoTableDef::SetSourceTableName](#setsourcetablename)|Задает значение, указывающее имя подключенной таблицы базы данных-источника.|
|[CDaoTableDef::SetValidationRule](#setvalidationrule)|Задает значение, которое проверяет данные в поля, как его изменить или добавить в таблицу.|
|[CDaoTableDef::SetValidationText](#setvalidationtext)|Задает значение, указывающее текст сообщения, которое отображает приложения, если значение объекта полей не удовлетворяет указанное правило проверки.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CDaoTableDef::m_pDAOTableDef](#m_pdaotabledef)|Указатель на базовый объект tabledef интерфейс DAO.|
|[CDaoTableDef::m_pDatabase](#m_pdatabase)|Базы данных-источника для этой таблицы.|

## <a name="remarks"></a>Примечания

Каждый объект базы данных DAO поддерживает набор данных с названием TableDefs, которая содержит все сохраненные объекты tabledef DAO.

Управлять определение таблицы с помощью `CDaoTableDef` объекта. Например, с их помощью можно выполнять следующее.

- Анализ структуры поля и индекс любой локальный, присоединяемых или внешние таблицы в базе данных.

- Вызовите `SetConnect` и `SetSourceTableName` функции-члены для вложенных таблиц, а `RefreshLink` функция-член для обновления подключений к присоединенные таблицы.

- Вызовите `CanUpdate` функция-член для определения того, если можно изменить определения полей в таблице.

- Возвращает или задает проверку условий, с помощью `GetValidationRule` и `SetValidationRule`и `GetValidationText` и `SetValidationText` функций-членов.

- Используйте `Open` функция-член для создания таблицы, общий или тип моментального снимка `CDaoRecordset` объекта.

    > [!NOTE]
    >  Классы баз данных DAO, отличаются от классов базы данных MFC на основе на Open Database Connectivity (ODBC). Все имена классов DAO базы данных имеют префикс «CDao». Вы можете по-прежнему доступ к источникам данных ODBC с помощью классов DAO. классы DAO обычно предлагают превосходные возможности, поскольку они определяются в ядре СУБД Microsoft Jet.

### <a name="to-use-tabledef-objects-either-to-work-with-an-existing-table-or-to-create-a-new-table"></a>Использование tabledef объектов для работы с существующей таблицы или создать новую таблицу

1. В любом случае сначала создать `CDaoTableDef` объекта, предоставляя указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) к которому принадлежит таблице.

1. Затем выполните следующие действия, в зависимости от желаемого.

   - Чтобы использовать существующий сохраненный таблицы, вызовите объект tabledef [откройте](#open) функция-член, указав имя сохраненного таблицы.

   - Чтобы создать новую таблицу, вызовите объект tabledef [создать](#create) функция-член, указав имя таблицы. Вызовите [CreateField](#createfield) и [CreateIndex](#createindex) Добавление полей и индексов в таблице.

   - Вызовите [Append](#append) для сохранения таблицы путем добавления его к tabledefs-коллекция базы данных. `Create` Помещает tabledef в открытом состоянии, поэтому после вызова метода `Create` не следует вызывать `Open`.

        > [!TIP]
        >  — Это самый простой способ создать сохраненный таблицы для их создания и сохранения их в базе данных с помощью Microsoft Access. Затем можно открыть и использовать их в коде MFC.

Чтобы использовать объект tabledef открытия или создания, создания и открытия `CDaoRecordset` объекта, указав имя tabledef с `dbOpenTable` значение в *nOpenType* параметра.

Использование для создания объекта tabledef `CDaoRecordset` объекта, вы обычно создайте или откройте tabledef, как описано выше, а затем создайте объект набора записей указателю на объект tabledef при вызове [CDaoRecordset::Open](../../mfc/reference/cdaorecordset-class.md#open). Tabledef, которое передается должны находиться в открытом состоянии. Дополнительные сведения см. в разделе класса [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).

Когда вы закончите, с помощью объекта tabledef, вызовите его [закрыть](../../mfc/reference/cdaorecordset-class.md#close) члена функции; затем удалите объект tabledef.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

`CDaoTableDef`

## <a name="requirements"></a>Требования

**Заголовок:** afxdao.h

##  <a name="append"></a>  CDaoTableDef::Append

Вызовите эту функцию-член, после вызова метода [создать](#create) для создания нового объекта tabledef сохранить tabledef в базе данных.

```
virtual void Append();
```

### <a name="remarks"></a>Примечания

Функция добавляет объект tabledefs-коллекция базы данных. Tabledef можно использовать в качестве временного объекта при его определении, не добавляя его, но если вы хотите сохранить и использовать его, необходимо вызвать `Append`.

> [!NOTE]
>  Если попытаться добавить неименованные tabledef (содержащий null или пустую строку), MFC вызывает исключение.

Дополнительные сведения см. в разделе «Добавить метод» в справке DAO.

##  <a name="canupdate"></a>  CDaoTableDef::CanUpdate

Вызывайте эту функцию члена, чтобы определить ли определение базовой таблицы `CDaoTableDef` объект может быть изменен.

```
BOOL CanUpdate();
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение, если в структуре таблицы (схемы) можно изменить (Добавить или удалить поля и индексов), иначе — 0.

### <a name="remarks"></a>Примечания

По умолчанию вновь созданная таблица базовый `CDaoTableDef` объект может быть изменен и присоединенная таблица базовая `CDaoTableDef` не удается обновить объект. Объект `CDaoTableDef` объект может быть обновлен, даже если результирующий набор записей не может быть обновлено.

Дополнительные сведения см. в разделе «Обновляемые свойство» в справке DAO.

##  <a name="cdaotabledef"></a>  CDaoTableDef::CDaoTableDef

Создает объект `CDaoTableDef`.

```
CDaoTableDef(CDaoDatabase* pDatabase);
```

### <a name="parameters"></a>Параметры

*pDatabase*<br/>
Указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта.

### <a name="remarks"></a>Примечания

После создания объекта, необходимо вызвать [создать](#create) или [откройте](#open) функция-член. Когда вы закончите с объектом, необходимо вызвать его [закрыть](#close) члена функции и уничтожать `CDaoTableDef` объекта.

##  <a name="close"></a>  CDaoTableDef::Close

Вызывайте эту функцию члена, чтобы закрыть и освободить объект tabledef.

```
virtual void Close();
```

### <a name="remarks"></a>Примечания

Обычно после вызова метода `Close`, удалить объект tabledef, если он был выделен с помощью **новый**.

Можно вызвать [откройте](#open) снова после вызова метода `Close`. Это позволяет повторно использовать объект tabledef.

Дополнительные сведения см. в разделе «Метод Close» в справке DAO.

##  <a name="create"></a>  CDaoTableDef::Create

Вызывайте эту функцию члена для создания новой таблицы сохраненный.

```
virtual void Create(
    LPCTSTR lpszName,
    long lAttributes = 0,
    LPCTSTR lpszSrcTable = NULL,
    LPCTSTR lpszConnect = NULL);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строку, содержащую имя таблицы.

*lAttributes*<br/>
Значение, соответствующее характеристикам таблиц, представленный объектом tabledef. Можно использовать побитового или для объединения любой из следующих констант:

|Константа|Описание|
|--------------|-----------------|
|`dbAttachExclusive`|Для баз данных, использующих базы данных Microsoft Jet указывает, что таблица является подключенной таблицы открыт для монопольного использования.|
|`dbAttachSavePWD`|Для баз данных, использующих базы данных Microsoft Jet указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.|
|`dbSystemObject`|Указывает, что таблица является системной таблицей, предоставляемые базы данных Microsoft Jet.|
|`dbHiddenObject`|Указывает, что таблица является таблицей скрытые, предоставляемые базы данных Microsoft Jet.|

*lpszSrcTable*<br/>
Указатель на строку, содержащую имя исходной таблицы. По умолчанию это значение инициализируется как NULL.

*lpszConnect*<br/>
Указатель на строку, содержащую строку подключения по умолчанию. По умолчанию это значение инициализируется как NULL.

### <a name="remarks"></a>Примечания

Как только вы присвоили имена tabledef, затем можно вызвать [Append](#append) для сохранения tabledef в tabledefs-коллекция базы данных. После вызова метода `Append`tabledef находится в открытом состоянии и его можно использовать для создания [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекта.

Дополнительные сведения см. в разделе «CreateTableDef Method» в справке DAO.

##  <a name="createfield"></a>  CDaoTableDef::CreateField

Вызывайте эту функцию члена, чтобы добавить поле в таблицу.

```
void CreateField(
    LPCTSTR lpszName,
    short nType,
    long lSize,
    long lAttributes = 0);

void CreateField(CDaoFieldInfo& fieldinfo);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строковое выражение, задающее имя этого поля.

*nType*<br/>
Значение, указывающее тип данных поля. Этот параметр может принимать одно из следующих значений:

|Тип|Размер (в байтах)|Описание|
|----------|--------------------|-----------------|
|`dbBoolean`|1 байт|BOOL|
|`dbByte`|BYTE|
|`dbInteger`|2|int|
|`dbLong`|4|long|
|`dbCurrency`|8|Валюта ( [COleCurrency](../../mfc/reference/colecurrency-class.md))|
|`dbSingle`|4|float|
|`dbDouble`|8|double|
|`dbDate`|8|Даты и времени ( [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|
|`dbText`|1 - 255|Текст ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|
|`dbLongBinary`|0|Long двоичный файл (OLE-объекта), [CLongBinary](../../mfc/reference/clongbinary-class.md) или [CByteArray](../../mfc/reference/cbytearray-class.md)|
|`dbMemo`|0|MEMO ( [CString](../../atl-mfc-shared/reference/cstringt-class.md))|

*lSize*<br/>
Значение, указывающее максимальный размер в байтах, поля, которое содержит текст, или фиксированный размер поля, содержащего текстовых или числовых. *LSize* параметр учитывается для всех, кроме текстовых полей.

*lAttributes*<br/>
Значение, соответствующее характеристикам поля и который можно объединить с помощью побитового или.

|Константа|Описание|
|--------------|-----------------|
|`dbFixedField`|Размер поля является фиксированным (по умолчанию для числовых полей).|
|`dbVariableField`|Размер поля является переменной (только для текстового поля).|
|`dbAutoIncrField`|Значение поля для новых записей автоматически увеличивается на единицу в уникальный длинное целое число, которое нельзя изменить. Поддерживается только для таблиц базы данных Microsoft Jet.|
|`dbUpdatableField`|Можно изменить значение поля.|
|`dbDescending`|Поле сортируются в нисходящем (Z - A или 100-0) порядке (применяется только к объекту поля в коллекции полей индекса объекта). Если опустить этой константы, поле сортируется по возрастанию (A - Z или 0 – 100) порядке (по умолчанию).|

*FieldInfo*<br/>
Ссылку на [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры.

### <a name="remarks"></a>Примечания

Объект `DAOField` (OLE) объект создается и добавляется в коллекцию полей `DAOTableDef` объект (OLE). Помимо использования для проверки свойств объекта, можно также использовать `CDaoFieldInfo` для построения для создания новых полей в tabledef входного параметра. Первая версия `CreateField` проще в использовании, но если требуется детальный контроль, можно использовать вторую версию `CreateField`, который принимает `CDaoFieldInfo` параметра.

Если вы используете версию `CreateField` , принимающий `CDaoFieldInfo` параметр, необходимо тщательно задать каждый из следующих членов `CDaoFieldInfo` структуры:

- `m_strName`

- `m_nType`

- `m_lSize`

- `m_lAttributes`

- `m_bAllowZeroLength`

Остальные члены `CDaoFieldInfo` должно быть присвоено **0**, FALSE или является пустой строкой, в зависимости от элемента, или `CDaoException` может произойти.

Дополнительные сведения см. в разделе «CreateField Method» в справке DAO.

##  <a name="createindex"></a>  CDaoTableDef::CreateIndex

Вызывайте эту функцию, чтобы добавить индекс к таблице.

```
void CreateIndex(CDaoIndexInfo& indexinfo);
```

### <a name="parameters"></a>Параметры

*indexinfo*<br/>
Ссылку на [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры.

### <a name="remarks"></a>Примечания

Индексы указывают порядок записей, доступных из таблиц базы данных и принимаются ли повторяющиеся записи. Индексы также обеспечивают эффективный доступ к данным.

Нет необходимости создавать индексы для таблиц, но в больших, неиндексированную таблиц, доступ к определенной записи или создание набора записей может занять много времени. С другой стороны, создание слишком много индексов замедляет работу обновления, добавлять и операции удаления, так как все индексы автоматически обновляются. Когда вы решаете, какие индексы для создания, учитывайте следующие факторы.

Следующие члены класса `CDaoIndexInfo` должна быть задана:

- `m_strName` Необходимо указать имя.

- `m_pFieldInfos` Должен указывать на массив `CDaoIndexFieldInfo` структуры.

- `m_nFields` Необходимо указать количество полей в массиве `CDaoFieldInfo` структуры.

Оставшиеся члены не учитывается, если устанавливается в значение FALSE. Кроме того `m_lDistinctCount` игнорируется во время создания индекса.

##  <a name="deletefield"></a>  CDaoTableDef::DeleteField

Эта функция члена удалить поле и сделать его недоступным.

```
void DeleteField(LPCTSTR lpszName);
void DeleteField(int nIndex);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строковое выражение, которое является именем существующего поля.

*nIndex*<br/>
Индекс поля в коллекции (с нуля) поля таблицы, для поиска по индексу.

### <a name="remarks"></a>Примечания

Эта функция-член можно использовать на новый объект, который не добавляются в базу данных или когда [CanUpdate](#canupdate) возвращает ненулевое значение.

Дополнительные сведения см. в разделе «Удаление Method» в справке DAO.

##  <a name="deleteindex"></a>  CDaoTableDef::DeleteIndex

Вызовите эту функцию-член для удаления индекса в базовой таблице.

```
void DeleteIndex(LPCTSTR lpszName);
void DeleteIndex(int nIndex);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строковое выражение, которое является именем существующего индекса.

*nIndex*<br/>
Индекс массива или объекта индекса в базе данных (с нуля) tabledefs-коллекция, для поиска по индексу.

### <a name="remarks"></a>Примечания

Эта функция-член можно использовать на новый объект, который еще не были добавлены в базу данных или когда [CanUpdate](#canupdate) возвращает ненулевое значение.

Дополнительные сведения см. в разделе «Удаление Method» в справке DAO.

##  <a name="getattributes"></a>  CDaoTableDef::GetAttributes

Для `CDaoTableDef` объекта, возвращаемое значение, указывающее характеристики таблицы, представленной `CDaoTableDef` объекта и может быть суммой эти константы:

```
long GetAttributes();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.

### <a name="remarks"></a>Примечания

|Константа|Описание|
|--------------|-----------------|
|`dbAttachExclusive`|Для баз данных, использующих базы данных Microsoft Jet указывает, что таблица является подключенной таблицы открыт для монопольного использования.|
|`dbAttachSavePWD`|Для баз данных, использующих базы данных Microsoft Jet указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.|
|`dbSystemObject`|Указывает, что таблица является системной таблицей, предоставляемые базы данных Microsoft Jet.|
|`dbHiddenObject`|Указывает, что таблица является таблицей скрытые, предоставляемые базы данных Microsoft Jet.|
|`dbAttachedTable`|Указывает, что таблица является подключенной таблицы из базы данных не ODBC, например в базе данных Paradox.|
|`dbAttachedODBC`|Указывает, что таблица является подключенной таблицы из базы данных ODBC, например Microsoft SQL Server.|

Системная таблица является таблицей, создаваемых ядром базы данных Jet (Майкрософт) для хранения различных внутренних данных.

Скрытые таблица представляет таблицу, созданную для временного использования базы данных Microsoft Jet.

Дополнительные сведения см. в разделе «Атрибуты свойство» в справке DAO.

##  <a name="getconnect"></a>  CDaoTableDef::GetConnect

Вызов этой функции-члена для получения строки подключения для источника данных.

```
CString GetConnect();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` объект, содержащий путь и тип базы данных для таблицы.

### <a name="remarks"></a>Примечания

Для `CDaoTableDef` , представляющий подключенной таблицы, `CString` объект состоит из одного или двух частей (описатель типа базы данных и путь к базе данных).

Путь, как показано в следующей таблице — это полный путь для каталога, содержащего файлы базы данных и должны начинаться с помощью идентификатора «базы данных =». В некоторых случаях (как с помощью Microsoft Jet и Microsoft Excel баз данных) под определенным именем файла включается в качестве аргумента путь к базе данных.

В таблице в [CDaoTableDef::SetConnect](#setconnect) показывает, возможно, база данных типов и их соответствующие спецификаторы базы данных и пути:

Для базовых таблиц базы данных Microsoft Jet, определитель является пустая строка (»»).

Если пароль является обязательным, однако не указано, драйвер ODBC входа диалоговое окно выводится первом обращении к таблице и снова при закрытии и повторном открытии соединения. Если есть подключенной таблицы `dbAttachSavePWD` атрибут, не будет отображаться запрос на вход, при повторном открытии таблицы.

Дополнительные сведения см. в разделе «Свойства подключения», в справке DAO.

##  <a name="getdatecreated"></a>  CDaoTableDef::GetDateCreated

Вызывайте эту функцию для определения даты и времени, в базовой таблице `CDaoTableDef` был создан объект.

```
COleDateTime GetDateCreated();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащее дату и время создания таблицы базового `CDaoTableDef` объекта.

### <a name="remarks"></a>Примечания

Параметры даты и времени являются производными от компьютера, на котором создания или последнего обновления базовой таблицы. В многопользовательской среде пользователи должны получить эти параметры непосредственно из файлового сервера, чтобы избежать несоответствия; то есть все клиенты должны использовать источник времени, «стандартный» — возможно, из одного сервера.

Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.

##  <a name="getdatelastupdated"></a>  CDaoTableDef::GetDateLastUpdated

Вызывайте эту функцию для определения даты и времени, в базовой таблице `CDaoTableDef` последнего обновления объекта.

```
COleDateTime GetDateLastUpdated();
```

### <a name="return-value"></a>Возвращаемое значение

Значение, содержащее дату и время в базовой таблице `CDaoTableDef` последнего обновления объекта.

### <a name="remarks"></a>Примечания

Параметры даты и времени являются производными от компьютера, на котором создания или последнего обновления базовой таблицы. В многопользовательской среде пользователи должны получить эти параметры непосредственно из файлового сервера, чтобы избежать несоответствия; то есть все клиенты должны использовать источник времени, «стандартный» — возможно, из одного сервера.

Дополнительные сведения см. в разделе «DateCreated LastUpdated свойства» в справке DAO.

##  <a name="getfieldcount"></a>  CDaoTableDef::GetFieldCount

Вызовите эту функцию-член для получения числа полей, определенных в таблице.

```
short GetFieldCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число полей в таблице.

### <a name="remarks"></a>Примечания

Если его значение равно 0, нет объектов в коллекции.

Дополнительные сведения см. в разделе «Свойство Count» в справке DAO.

##  <a name="getfieldinfo"></a>  CDaoTableDef::GetFieldInfo

Вызов для получения различного рода сведения о поле, определенное в tabledef эта функция-член.

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
Индекс поля объекта в коллекции (с нуля) поля таблицы, для поиска по индексу.

*FieldInfo*<br/>
Ссылку на [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры.

*dwInfoOptions*<br/>
Параметры, укажите, какие сведения о поле для извлечения. А также как они вызвать функцию возврата здесь перечислены доступные параметры:

- `AFX_DAO_PRIMARY_INFO` (По умолчанию) Имя, тип, размер, атрибуты. Используйте этот параметр для наибольшую производительность.

- `AFX_DAO_SECONDARY_INFO` Сведения об основном, а также: порядковый номер позиции, необходимости разрешить нулевой длины, порядок сортировки, имя внешнего, исходное поле исходной таблицы

- `AFX_DAO_ALL_INFO` Основной и дополнительной информации, а также: значение по умолчанию правило проверки, текст проверки

*lpszName*<br/>
Указатель на имя поля объекта, для поиска по имени. Имя является строкой с длиной до 64 символов, который дает уникальное название поля.

### <a name="remarks"></a>Примечания

Одну версию функции позволяет искать поле по индексу. Другая версия позволяет искать поле по имени.

Описание сведений, возвращаемых, см. в разделе [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют элементам данных, перечисленные выше в описании *dwInfoOptions*. При запросе сведений на одном уровне, вы получите сведения о всех предыдущих уровней.

Дополнительные сведения см. в разделе «Атрибуты свойство» в справке DAO.

##  <a name="getindexcount"></a>  CDaoTableDef::GetIndexCount

Вызывайте эту функцию члена, чтобы получить количество индексов для таблицы.

```
short GetIndexCount();
```

### <a name="return-value"></a>Возвращаемое значение

Число индексов для таблицы.

### <a name="remarks"></a>Примечания

Если его значение равно 0, существует ни одного индекса в коллекции.

Дополнительные сведения см. в разделе «Свойство Count» в справке DAO.

##  <a name="getindexinfo"></a>  CDaoTableDef::GetIndexInfo

Вызов для получения различного рода сведения об индексе, определенные в tabledef эта функция-член.

```
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

*nIndex*<br/>
Числовой индекс, индекс объекта в коллекции (с нуля) индексы таблицы, для поиска по его позиции в коллекции.

*indexinfo*<br/>
Ссылку на [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры.

*dwInfoOptions*<br/>
Параметры, укажите, какие сведения об индексе для извлечения. А также как они вызвать функцию возврата здесь перечислены доступные параметры:

- `AFX_DAO_PRIMARY_INFO` Имя, сведения о поле, поля. Используйте этот параметр для наибольшую производительность.

- `AFX_DAO_SECONDARY_INFO` Сведения об основном, плюс: основной, Unique, Clustered, игнорировать значения NULL, необходимости внешнего

- `AFX_DAO_ALL_INFO` Основной и дополнительной информации, а также: числа различных объектов

*lpszName*<br/>
Указатель на имя объект индекса, для поиска по имени.

### <a name="remarks"></a>Примечания

Одну версию функции позволяет искать индекса по его позиции в коллекции. Другая версия позволяет искать индекса по имени.

Описание сведений, возвращаемых, см. в разделе [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) структуры. Эта структура содержит члены, которые соответствуют элементам данных, перечисленные выше в описании *dwInfoOptions*. При запросе сведений на одном уровне, вы получите сведения о всех предыдущих уровней.

Дополнительные сведения см. в разделе «Атрибуты свойство» в справке DAO.

##  <a name="getname"></a>  CDaoTableDef::GetName

Вызывайте эту функцию члена, чтобы получить определенное пользователем имя базовой таблицы.

```
CString GetName();
```

### <a name="return-value"></a>Возвращаемое значение

Определяемое пользователем имя для таблицы.

### <a name="remarks"></a>Примечания

Это имя начинается с буквы и может содержать не более 64 символов. Он может включать цифры и символы подчеркивания, но не может содержать знаки пунктуации и пробелы.

Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

##  <a name="getrecordcount"></a>  CDaoTableDef::GetRecordCount

Вызывайте эту функцию члена, чтобы узнать, сколько записей в `CDaoTableDef` объекта.

```
long GetRecordCount();
```

### <a name="return-value"></a>Возвращаемое значение

Количество записей, доступных в объекте tabledef.

### <a name="remarks"></a>Примечания

Вызов `GetRecordCount` для табличного типа `CDaoTableDef` объект отражает приблизительное количество записей в таблице и немедленно влияет как добавления и удаления записей в таблице. Откат транзакции будут отображаться как часть счетчик записей до вызова метода [CDaoWorkSpace::CompactDatabase](../../mfc/reference/cdaoworkspace-class.md#compactdatabase). Объект `CDaoTableDef` объект без записей имеет свойство счетчик записей, равным 0. При работе с таблицами или базами данных ODBC `GetRecordCount` всегда возвращает значение -1.

Дополнительные сведения см. в разделе «RecordCount свойство» в справке DAO.

##  <a name="getsourcetablename"></a>  CDaoTableDef::GetSourceTableName

Вызовите эту функцию-член для извлечения имени подключенной таблицы в базы данных-источника.

```
CString GetSourceTableName();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , указывающий имя источника объекта подключенной таблицы, или пустая строка, если для таблицы данных в собственном формате.

### <a name="remarks"></a>Примечания

Подключенной таблицы является таблицей в другой базе данных, связанной с базой данных Microsoft Jet. Данные для вложенных таблиц остается внешней базы данных, где ими можно управлять другими приложениями.

Дополнительные сведения см. в разделе «SourceTableName свойство» в справке DAO.

##  <a name="getvalidationrule"></a>  CDaoTableDef::GetValidationRule

Вызовите эту функцию-член для извлечения правила проверки для tabledef.

```
CString GetValidationRule();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` объект, который проверяет данные в поля, как его изменить или добавить в таблицу.

### <a name="remarks"></a>Примечания

Правила проверки, используемых при операции обновления. Если tabledef содержит правило проверки, обновления, tabledef должно соответствовать предварительно определенные условия, перед изменением данных. Если изменения не соответствуют критериям, исключение, содержащее значимость [GetValidationText](#getvalidationtext) возникает исключение. Для `CDaoTableDef` объекта, это `CString` только для чтения для подключенной таблицы и чтение и запись для базовой таблицы.

Дополнительные сведения см. в разделе «Значение» в справке DAO.

##  <a name="getvalidationtext"></a>  CDaoTableDef::GetValidationText

Вызывайте эту функцию, чтобы получить строку для отображения, когда пользователь вводит данные, соответствующие правила проверки.

```
CString GetValidationText();
```

### <a name="return-value"></a>Возвращаемое значение

Объект `CString` , указывающий текст, отображаемый, если пользователь вводит данные, соответствующие правила проверки.

### <a name="remarks"></a>Примечания

Для `CDaoTableDef` объекта, это `CString` только для чтения для подключенной таблицы и чтение и запись для базовой таблицы.

Дополнительные сведения см. в разделе «Свертыванию» в справке DAO.

##  <a name="isopen"></a>  CDaoTableDef::IsOpen

Вызывайте эту функцию члена, чтобы определить, является ли `CDaoTableDef` объекта в данный момент открыт.

```
BOOL IsOpen() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ненулевое значение `CDaoTableDef` объект является открытым; в противном случае — 0.

### <a name="remarks"></a>Примечания

##  <a name="m_pdatabase"></a>  CDaoTableDef::m_pDatabase

Содержит указатель на [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) объекта для этой таблицы.

### <a name="remarks"></a>Примечания

##  <a name="m_pdaotabledef"></a>  CDaoTableDef::m_pDAOTableDef

Содержит указатель на интерфейс OLE для базового объекта DAO tabledef `CDaoTableDef` объекта.

### <a name="remarks"></a>Примечания

Используйте этот указатель, если требуется доступ к интерфейсу DAO напрямую.

##  <a name="open"></a>  CDaoTableDef::Open

Вызов, чтобы открыть tabledef эта функция-член, ранее сохраненных в базе данных, TableDef элемента коллекции.

```
virtual void Open(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строку, которая указывает имя таблицы.

### <a name="remarks"></a>Примечания

##  <a name="refreshlink"></a>  CDaoTableDef::RefreshLink

Вызывайте эту функцию члена, чтобы обновить сведения о соединении для подключенной таблицы.

```
void RefreshLink();
```

### <a name="remarks"></a>Примечания

Изменить сведения о соединении для подключенной таблицы путем вызова [SetConnect](#setconnect) соответствующего `CDaoTableDef` объекта, а затем с помощью `RefreshLink` функция-член для обновления данных. При вызове `RefreshLink`, свойства вложенные таблицы, не изменяются.

Чтобы принудительно измененные сведения о подключении вступили в силу, все открытые [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) объекты в зависимости от этого tabledef должны быть закрыты.

Дополнительные сведения см. в разделе «RefreshLink Method» в справке DAO.

##  <a name="setattributes"></a>  CDaoTableDef::SetAttributes

Задает значение, указывающее один или несколько характеристик `CDaoTableDef` объекта.

```
void SetAttributes(long lAttributes);
```

### <a name="parameters"></a>Параметры

*lAttributes*<br/>
Характеристики таблицы, представленной `CDaoTableDef` объекта и может быть суммой эти константы:

|Константа|Описание|
|--------------|-----------------|
|`dbAttachExclusive`|Для баз данных, использующих базы данных Microsoft Jet указывает, что таблица является подключенной таблицы открыт для монопольного использования.|
|`dbAttachSavePWD`|Для баз данных, использующих базы данных Microsoft Jet указывает, что идентификатор пользователя и пароль для подключенной таблицы сохраняются сведения о соединении.|
|`dbSystemObject`|Указывает, что таблица является системной таблицей, предоставляемые базы данных Microsoft Jet.|
|`dbHiddenObject`|Указывает, что таблица является таблицей скрытые, предоставляемые базы данных Microsoft Jet.|

### <a name="remarks"></a>Примечания

При установке нескольких атрибутов, их можно объединить сложив соответствующие константы, с помощью битового оператора или. Параметр `dbAttachExclusive` для неприсоединенных таблицы создает исключение. Объединение следующие значения, также создают исключение:

- **dbAttachExclusive &#124; dbAttachedODBC**

- **dbAttachSavePWD &#124; dbAttachedTable**

Дополнительные сведения см. в разделе «Атрибуты свойство» в справке DAO.

##  <a name="setconnect"></a>  CDaoTableDef::SetConnect

Для `CDaoTableDef` , представляющий подключенной таблицы, строковый объект состоит из одного или двух частей (описатель типа базы данных и путь к базе данных).

```
void SetConnect(LPCTSTR lpszConnect);
```

### <a name="parameters"></a>Параметры

*lpszConnect*<br/>
Указатель на строковое выражение, которое указывает дополнительные параметры, которые будут передаваться в ODBC или устанавливаемые драйверы ISAM.

### <a name="remarks"></a>Примечания

Путь, как показано в следующей таблице — это полный путь для каталога, содержащего файлы базы данных и должны начинаться с помощью идентификатора «базы данных =». В некоторых случаях (как с помощью Microsoft Jet и Microsoft Excel баз данных) под определенным именем файла включается в качестве аргумента путь к базе данных.

> [!NOTE]
>  Не используйте пробелы вокруг знака равенства в инструкциях путь в формате «базы данных = диск:\\\path». Это приведет к возникновению исключения и сбою подключения.

Следующая таблица показывает, возможно, база данных типов и их соответствующие спецификаторы базы данных и пути:

|Тип базы данных|Описатель|Путь|
|-------------------|---------------|----------|
|Базы данных с помощью базы данных Jet|"[ `database`];"|" `drive`:\\\ *путь*\\\ *filename*. MDB»|
|dBASE III|«dBASE III;»|" `drive`:\\\ *путь*"|
|dBASE IV|«dBASE IV;»|" `drive`:\\\ *путь*"|
|dBASE 5|«dBASE 5.0;»|" `drive`:\\\ *путь*"|
|Paradox 3.x|«Paradox 3.x;»|" `drive`:\\\ *путь*"|
|Paradox 4.x|«Paradox 4.x;»|" `drive`:\\\ *путь*"|
|Paradox 5.x|«Paradox 5.x;»|" `drive`:\\\ *путь*"|
|Excel 3.0|«Excel 3.0;»|" `drive`:\\\ *путь*\\\ *filename*. XLS»|
|Excel 4.0|«Excel 4.0;»|" `drive`:\\\ *путь*\\\ *filename*. XLS»|
|Excel 5.0 или Excel 95|«Excel 5.0;»|" `drive`:\\\ *путь*\\\ *filename*. XLS»|
|Excel 97|«Excel 8.0»;|" `drive`:\\\ *путь*\ *filename*. XLS»|
|Импорт HTML|«Импорт HTML»;|" `drive`:\\\ *путь*\ *filename*"|
|Экспорт HTML-кода|«Экспорт HTML-кода»;|" `drive`:\\\ *путь*"|
|Text|«Текст»;|«диск:\\\path»|
|ODBC|«ODBC; Базы данных = `database`; UID = *пользователя*; PWD = *пароль*; DSN = *datasourcename;* LOGINTIMEOUT = *секунды;*" (Это может быть полной строки соединения для всех серверов, это всего лишь примером. Это крайне важно не содержат пробелы между параметрами.)|Нет|
|Exchange|«Exchange;<br /><br /> MAPILEVEL = *folderpath*;<br /><br /> [TABLETYPE = {0 &AMP;#124; 1};]<br /><br /> [Профиль = *профиль*;]<br /><br /> [PWD = *пароль*;]<br /><br /> [DATABASE = `database`;]»|*«диск*:\\\ *путь*\\\ *filename*. MDB»|

> [!NOTE]
>  Начиная с DAO 3.5 Btrieve больше не поддерживается.

Необходимо использовать двойной обратной косой черты (\\\\) в строке подключения. Если вы изменили свойства существующего соединения с помощью `SetConnect`, после этого необходимо вызвать [RefreshLink](#refreshlink). При инициализации свойства соединения, с помощью `SetConnect`, вам потребуется не вызов `RefreshLink`, но если вы решите сделать, сначала добавить tabledef.

Если пароль является обязательным, однако не указано, драйвер ODBC входа диалоговое окно выводится первом обращении к таблице и снова при закрытии и повторном открытии соединения.

Можно задать строку подключения для `CDaoTableDef` , указав исходный аргумент для `Create` функция-член. Вы можете проверить параметр, чтобы определить тип, путь, идентификатор пользователя, пароль или источника данных ODBC базы данных. Дополнительные сведения см. в документации для заданного драйвера.

Дополнительные сведения см. в разделе «Свойства подключения», в справке DAO.

##  <a name="setname"></a>  CDaoTableDef::SetName

Вызывайте эту функцию члена, чтобы задать пользовательское имя для таблицы.

```
void SetName(LPCTSTR lpszName);
```

### <a name="parameters"></a>Параметры

*lpszName*<br/>
Указатель на строковое выражение, указывающее имя таблицы.

### <a name="remarks"></a>Примечания

Имя должно начинаться с буквы и может содержать не более 64 символов. Он может включать цифры и символы подчеркивания, но не может содержать знаки пунктуации и пробелы.

Дополнительные сведения см. в разделе «Имя свойства» в справке DAO.

##  <a name="setsourcetablename"></a>  CDaoTableDef::SetSourceTableName

Вызов для указания имя подключенной таблицы или имя базовой таблицы, на котором эта функция-член `CDaoTableDef` основан объект, как оно существует в исходном источнике данных.

```
void SetSourceTableName(LPCTSTR lpszSrcTableName);
```

### <a name="parameters"></a>Параметры

*lpszSrcTableName*<br/>
Указатель на строковое выражение, указывающее имя таблицы внешней базы данных. Для базовой таблицы, параметр является пустой строкой (»»).

### <a name="remarks"></a>Примечания

Затем необходимо вызвать [RefreshLink](#refreshlink). Значение этого свойства является пустым для базовой таблицы и чтение и запись для подключенной таблицы или объекта не добавляется в коллекцию.

Дополнительные сведения см. в разделе «SourceTableName свойство» в справке DAO.

##  <a name="setvalidationrule"></a>  CDaoTableDef::SetValidationRule

Вызывайте эту функцию члена, чтобы задать правила проверки для tabledef.

```
void SetValidationRule(LPCTSTR lpszValidationRule);
```

### <a name="parameters"></a>Параметры

*lpszValidationRule*<br/>
Указатель на строковое выражение, проверяющее операции.

### <a name="remarks"></a>Примечания

Правила проверки, используемых при операции обновления. Если tabledef содержит правило проверки, обновления, tabledef должно соответствовать предварительно определенные условия, перед изменением данных. Если изменения не соответствуют критериям, исключение, содержащее текст [GetValidationText](#getvalidationtext) отображается.

Проверка поддерживается только для баз данных, использующих базы данных Microsoft Jet. Выражение не может ссылаться на определяемые пользователем функции, статистические функции, статистические функции SQL или запросы. Правила проверки для `CDaoTableDef` объект могут ссылаться на несколько полей в этом объекте.

Например, для поля с именем *hire_date* и *termination_date*, возможно, правила проверки:

[!code-cpp[NVC_MFCDatabase#34](../../mfc/codesnippet/cpp/cdaotabledef-class_1.cpp)]

Дополнительные сведения см. в разделе «Значение» в справке DAO.

##  <a name="setvalidationtext"></a>  CDaoTableDef::SetValidationText

Эта функция-член для задания текста исключения правила проверки для вызова `CDaoTableDef` объект с базовой таблицы поддерживается ядром СУБД Microsoft Jet.

```
void SetValidationText(LPCTSTR lpszValidationText);
```

### <a name="parameters"></a>Параметры

*lpszValidationText*<br/>
Указатель на строковое выражение, указывающее текст, отображаемый, если введены данные, является недопустимым.

### <a name="remarks"></a>Примечания

Невозможно задать текст проверки вложенные таблицы.

Дополнительные сведения см. в разделе «Свертыванию» в справке DAO.

## <a name="see-also"></a>См. также

[Класс CObject](../../mfc/reference/cobject-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Класс CDaoDatabase](../../mfc/reference/cdaodatabase-class.md)<br/>
[Класс CDaoRecordset](../../mfc/reference/cdaorecordset-class.md)
