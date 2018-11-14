---
title: Поддержка наборов строк схемы
ms.date: 11/04/2016
helpviewer_keywords:
- schema rowsets
- OLE DB consumer templates, schema rowsets
- OLE DB providers, schema rowsets
- OLE DB, schema rowsets
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
ms.openlocfilehash: 6046bcb1b99e446974a3b4fae11d0021778bf526
ms.sourcegitcommit: c40469825b6101baac87d43e5f4aed6df6b078f5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2018
ms.locfileid: "51556885"
---
# <a name="supporting-schema-rowsets"></a>Поддержка наборов строк схемы

Наборы строк схемы позволяют пользователям получить сведения о хранилище данных, не зная ее базовую структуру, или схему. Например хранилище данных есть таблицы, упорядоченные в пользовательской иерархии, поэтому будет невозможно получить сведения о схеме, читая его. (Еще один пример мастера Visual C++ используйте наборы строк схемы для создания методов доступа для пользователя.) Чтобы разрешить пользователю это сделать, объект сеанса поставщика представляет методы на [IDBSchemaRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms713686(v=vs.85)) интерфейс. В приложениях Visual C++, используйте [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) класс для реализации `IDBSchemaRowset`.

`IDBSchemaRowsetImpl` поддерживает следующие методы:

- [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) проверяет допустимость ограничений относительно набора строк схемы.

- [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) реализует функцию создателя COM объект для объекта, указанного параметром шаблона.

- [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) указывает, какие ограничения, поддерживаемые в определенном наборе строк схемы.

- [IDBSchemaRowset::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) возвращает набор строк схемы (наследуется от интерфейса).

- [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) возвращает список наборов строк схемы, доступных `IDBSchemaRowsetImpl::GetRowset` (наследуется от интерфейса).

## <a name="atl-ole-db-provider-wizard-support"></a>Поддержка мастера ATL OLE DB поставщика

**Мастер поставщика ATL OLE DB** создает три класса схемы в файле заголовка сеанса:

- **C**<em>ShortName</em>**SessionTRSchemaRowset**

- **C**<em>ShortName</em>**SessionColSchemaRowset**

- **C**<em>ShortName</em>**SessionPTSchemaRowset**

Эти классы отвечать на запросы потребителей сведений о схеме; Обратите внимание на то, что спецификация OLE DB требует поддержки этих наборов строк схемы:

- **C**<em>ShortName</em>**SessionTRSchemaRowset** обрабатывает запросы сведений о таблице (набора строк схемы DBSCHEMA_TABLES).

- **C**<em>ShortName</em>**SessionColSchemaRowset** обрабатывает запросы сведений о столбце (набора строк схемы DBSCHEMA_COLUMNS). Мастер предоставляет пример реализации для этих классов, которые возвращают сведения о схеме для поставщика DOS.

- **C**<em>ShortName</em>**SessionPTSchemaRowset** обрабатывает запросы для схемы сведения о типе поставщика (DBSCHEMA_PROVIDER_TYPES набора строк схемы). Реализация по умолчанию, предоставленным мастером, возвращается значение s_ок.

Вы можете настраивать эти классы для обработки сведений о схеме, подходящие для вашего поставщика.

- В **C**<em>ShortName</em>**SessionTRSchemaRowset**, необходимо заполнить поля каталога, таблицы и описание (`trData.m_szType`, `trData.m_szTable`и `trData.m_szDesc`). В примере, создаваемые мастером используется только одна строка (таблица). Другие поставщики могут возвращать более одной таблицы.

- В **C**<em>ShortName</em>**SessionColSchemaRowset**, передайте имя таблицы как `DBID`.

## <a name="setting-restrictions"></a>Задание ограничений

Важным принципом в поддержке набора строк схемы является установка ограничения, которые можно сделать с помощью `SetRestrictions`. Ограничения позволяют выбирать только совпадающие строки (например, поиск всех столбцов в таблице MyTable). Ограничения являются необязательными, и если не поддерживается ни одно ограничение (по умолчанию), всегда возвращаются все данные. Пример поставщика, поддерживает ли ограничения, см. в разделе [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) образца.

## <a name="setting-up-the-schema-map"></a>Настройка схемы

Настройка сопоставления в схеме следующего вида в Session.h в этом примере:

```cpp
BEGIN_SCHEMA_MAP(CUpdateSession)
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)
END_SCHEMA_MAP()
```

Для поддержки `IDBSchemaRowset`, должен поддерживать DBSCHEMA_TABLES, DBSCHEMA_COLUMNS и DBSCHEMA_PROVIDER_TYPES. Можно добавить дополнительные наборы строк схем по своему усмотрению.

Объявите класс набора строк схемы с `Execute` метода, такого как `CUpdateSessionTRSchemaRowset` в `UpdatePV`:

```cpp
class CUpdateSessionTRSchemaRowset :
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,
                              CTABLESRow, CUpdateSession >
...
// Execute looks like this; what pointers does the consumer use?
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,
                    ULONG cRestrictions, const VARIANT* rgRestrictions)
```

`CUpdateSession` наследует от `IDBSchemaRowsetImpl`, поэтому он поддерживает все методы обработки ограничений. С помощью `CSchemaRowsetImpl`, объявляет три дочерних класса (перечислены в схеме выше): `CUpdateSessionTRSchemaRowset`, `CUpdateSessionColSchemaRowset`, и `CUpdateSessionPTSchemaRowset`. Каждый из этих дочерних классов имеет `Execute` метод, который обрабатывает соответствующий набор ограничений (критерии поиска). Каждый `Execute` метод сравнивает значения *cRestrictions* и *rgRestrictions* параметров. Описание этих параметров см. в разделе [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).

Дополнительные сведения о том, какие ограничения соответствуют определенному набору строк схемы, см. в таблице GUID наборов строк схем в [IDBSchemaRowset](https://docs.microsoft.com/previous-versions/windows/desktop/ms713686(v=vs.85)) в **Справочник программиста OLE DB по** в пакете SDK для Windows .

Например если ограничения TABLE_NAME поддерживается на DBSCHEMA_TABLES, то сделайте следующее:

Во-первых просмотрите DBSCHEMA_TABLES и см. в разделе, что он поддерживает четыре ограничения (в порядке).

|Ограничение набора строк схемы|Значение ограничения|
|-------------------------------|-----------------------|
|TABLE_CATALOG|0x1 (двоичные 1)|
|TABLE_SCHEMA|0x2 (двоичный 10)|
|TABLE_NAME|0x4 (двоичный 100)|
|TABLE_TYPE|0x8 (двоичный 1000)|

Затем идет одному биту на каждый ограниченного использования программ. Так как требуется только поддержка TABLE_NAME, необходим возврат 0x4 в `rgRestrictions` элемент. При поддержке значениям TABLE_CATALOG, а также TABLE_NAME будет возвращать 0x5 (двоичный 101).

По умолчанию реализация возвращает 0 (не поддерживает каких-либо ограничений) для любого запроса. UpdatePV является примером поставщика, который поддерживает ограничения.

### <a name="example"></a>Пример

Этот код берется из [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) образца. `UpdatePv` поддерживает три наборы строк схемы, необходимый: DBSCHEMA_TABLES, DBSCHEMA_COLUMNS и DBSCHEMA_PROVIDER_TYPES. Пример реализации поддержки схемы в поставщике: в этом разделе вы ознакомитесь с набора строк DBSCHEMA_TABLE.

> [!NOTE]
> Пример кода может отличаться от приведенного в примере; пример кода следует рассматривать в качестве более новой версии.

Добавление поддержки схемы первым делом для определения ограничений вы собираетесь поддерживать. Чтобы определить, какие ограничения, доступные для набора строк схемы, просмотрите спецификации OLE DB для определения `IDBSchemaRowset`. Следующие главному определению отобразится таблица, содержащая имя набора строк схемы, число ограничений и столбцов ограничений. Выберите набор строк схемы, необходимые для поддержки и запомните или запишите число и столбцов ограничений. Например DBSCHEMA_TABLES поддерживает четыре ограничения (значениям TABLE_CATALOG, TABLE_SCHEMA, TABLE_NAME и TABLE_TYPE):

```cpp
void SetRestrictions(ULONG cRestrictions, GUID* rguidSchema,
   ULONG* rgRestrictions)
{
    for (ULONG l=0; l<cRestrictions; l++)
    {
        if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))
            rgRestrictions[l] = 0x0C;
        else if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_COLUMNS))
                 rgRestrictions[l] = 0x04;
             else if (InlineIsEqualGUID(rguidSchema[l],
                                        DBSCHEMA_PROVIDER_TYPES))
                      rgRestrictions[l] = 0x00;
   }
}
```

Бит представляет каждый столбец ограничений. Если вы хотите поддерживать ограничение (то есть можно запросить в нем), значение бита 1. Если вы не хотите поддерживать ограничение, присваивается нулевое значение разряда. Из строки в представленном выше коде `UpdatePV` поддерживает TABLE_NAME и TABLE_TYPE ограничения на набор строк DBSCHEMA_TABLES. Это третье (Битовая маска 100) и четвертой ограничения (Битовая маска 1000). Таким образом, битовая маска для `UpdatePv` 1100 (или 0x0C):

```cpp
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))
    rgRestrictions[l] = 0x0C;
```

Следующие `Execute` функция похожа на аналогичные в обычных наборах строк. У вас есть три аргумента: *pcRowsAffected*, *cRestrictions*, и *rgRestrictions*. *PcRowsAffected* переменная является параметром output, что поставщик может возвращать количество строк в наборе строк схемы. *CRestrictions* параметр является входным параметром, содержащим число ограничений, переданных потребителем поставщику. *RgRestrictions* параметр представляет собой массив значений типа VARIANT, которые содержат значений ограничений.

```cpp
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,
                const VARIANT* rgRestrictions)
```

*CRestrictions* переменная основана на общее число ограничений для набора строк схемы, независимо от того, поддерживаемыми поставщиком. Поскольку UpdatePv поддерживает два ограничения (третье и четвертое), этот код осуществляет только поиск *cRestrictions* значение больше или равен трем.

Значение для ограничения TABLE_NAME хранится в *rgRestrictions [2]* (опять же, третье ограничение с индексацией равно 2). Проверьте, что ограничение не VT_EMPTY, чтобы гарантировать поддержку. Обратите внимание на то, что VT_NULL не соответствует значение VT_EMPTY. VT_NULL указывает на действительное значение ограничения.

`UpdatePv` Определение имени таблицы — это полный путь к текстовому файлу. Извлеките значение ограничения и затем попробуйте открыть файл, чтобы убедиться, что файл существует. Если файл не существует, верните значение s_ок. Это может показаться немного назад, но код действительно сообщается потребитель является то, что существуют таблицы, не поддерживаемые по имени, указанному. Возвращаемое значение S_OK означает, что правильность выполнения кода.

```cpp
USES_CONVERSION;
enum {
            sizeOfszFile = 255
};
CTABLESRow  trData;
FILE        *pFile = NULL;
TCHAR       szFile[ sizeOfszFile ];
errcode     err = 0;

// Handle any restrictions sent to us. This only handles
// the TABLE_NAME & TABLE_TYPE restictions (the 3rd and 4th
// restrictions in DBSCHEMA_TABLES...look in IDBSchemaRowsets
// in part 2 of the prog. ref) so your restrictions are 0x08 & 0x04
// for a total of (0x0C)
if (cRestrictions >= 3 && rgRestrictions[2].vt != VT_EMPTY)
{
    CComBSTR bstrName = rgRestrictions[2].bstrVal;
    if ((rgRestrictions[2].vt == VT_BSTR) && (bstrName != (BSTR)NULL))
    {
        // Check to see if the file exists
        _tcscpy_s(&szFile[0], sizeOfszFile, OLE2T(bstrName));
        if (szFile[0] == _T('\0') ||
           ((err = _tfopen(&pFile, &szFile[0], _T("r"))) == 0))
        {
            return S_OK;// Their restriction was invalid return no data
        }
        else
        {
            fclose(pFile);
        }
    }
}
```

Поддержка четвертого ограничения (TABLE_TYPE) похоже на третье ограничение. Проверьте, что значение не VT_EMPTY. Это ограничение только возвращает табличный тип TABLE. Чтобы определить допустимые значения для DBSCHEMA_TABLES, просмотрите **приложении Б** из **Справочник программиста OLE DB по** в разделе строк таблицы.

```cpp
// TABLE_TYPE restriction:
if (cRestrictions >=4 && rgRestrictions[3].vt != VT_EMPTY)
{
    CComBSTR bstrType = rgRestrictions[3].bstrVal;
    if ((rgRestrictions[3].vt == VT_BSTR) && (bstrType != (BSTR)NULL))
    {
        // This is kind of a blind restriction.
        // This only actually supports
        // TABLES so if you get anything else,
        // just return an empty rowset.
        if (_tcscmp(_T("TABLE"), OLE2T(bstrType)) != 0)
            return S_OK;
    }
}
```

Это фактически создаются запись строк для набора строк. Переменная `trData` соответствует `CTABLESRow`, структуру, определенных в шаблонах поставщика OLE DB. `CTABLESRow` соответствует определению таблицы набора строк в **приложении Б** спецификации OLE DB. У вас только одна строка для добавления, так как одновременно может поддерживать только одну таблицу.

```cpp
// Bring over the data:
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);

wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);

wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());
```

`UpdatePV` Задает только три столбца: TABLE_NAME TABLE_TYPE и описание. Запомните или запишите столбцы, для которых осуществляется возврат информации, так как эти сведения потребуются при реализации `GetDBStatus`:

```cpp
    _ATLTRY
    {
        m_rgRowData.Add(trData);
    }
    _ATLCATCHALL()
    {
        return E_OUTOFMEMORY;
    }
    //if (!m_rgRowData.Add(trData))
    //    return E_OUTOFMEMORY;
    *pcRowsAffected = 1;
    return S_OK;
}
```

`GetDBStatus` Функции важно для правильной работы набора строк схемы. Так как не возвращают данные для каждого столбца в наборе строк таблицы, необходимо указать, какие столбцы возвращают данные о, а какие нет.

```cpp
virtual DBSTATUS GetDBStatus(CSimpleRow* , ATLCOLUMNINFO* pColInfo)
{
    ATLASSERT(pColInfo != NULL);

    switch(pColInfo->iOrdinal)
    {
    case 3:     // TABLE_NAME
    case 4:     // TABLE_TYPE
    case 6:     // DESCRIPTION
        return DBSTATUS_S_OK;
        break;
    default:
        return DBSTATUS_S_ISNULL;
    break;
    }
}
```

Так как ваш `Execute` функция возвращает данные для полей TABLE_NAME TABLE_TYPE и описание из набора строк таблицы, она позволяет заглянуть в **приложении Б** спецификации OLE DB и определить (посчитав сверху) Если они порядковые номера, 3, 4 и 6. Для каждого из этих столбцов возвращать DBSTATUS_S_OK. Для всех других столбцов возвращают значение DBSTATUS_S_ISNULL. Важно для возвращения состояния, так как объект-получатель может не понять, что возвращаемое значение — NULL или что-то другое. Опять же Обратите внимание на то, что значение NULL не эквивалентно пустой.

Дополнительные сведения о интерфейс набора строк схемы OLE DB, см. в разделе [IDBSchemaRowset](../../data/oledb/idbschemarowsetimpl-class.md) интерфейс **Справочник программиста OLE DB по**.

Сведения о том, как пользователи могут применять `IDBSchemaRowset` методы, см. в разделе [получение метаданных в схеме набора строк](../../data/oledb/obtaining-metadata-with-schema-rowsets.md).

Пример поставщика, поддерживающего наборы строк схемы, см. в разделе [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV) образца.

## <a name="see-also"></a>См. также

[Дополнительные способы использования поставщика](../../data/oledb/advanced-provider-techniques.md)
