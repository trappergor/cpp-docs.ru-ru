---
title: Поддержка наборов строк схемы
ms.date: 11/04/2016
helpviewer_keywords:
- schema rowsets
- OLE DB consumer templates, schema rowsets
- OLE DB providers, schema rowsets
- OLE DB, schema rowsets
ms.assetid: 71c5e14b-6e33-4502-a2d9-a1dc6d6e9ba0
ms.openlocfilehash: 09af59d97ab87c66a0a7096e72cc7b92bc3a5dbf
ms.sourcegitcommit: 00e26915924869cd7eb3c971a7d0604388abd316
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2019
ms.locfileid: "65525272"
---
# <a name="supporting-schema-rowsets"></a>Поддержка наборов строк схемы

Наборы строк схемы позволяют объектам-получателям получать сведения о хранилище данных, не зная его базовой структуры или схемы. Например, в хранилище данных могут быть таблицы, организованные в определенной пользователем иерархии, поэтому невозможно будет узнать схему, не прочитав ее. (В качестве другого примера мастера Visual C++ используют наборы строк схемы, чтобы создать метод доступа для объекта-получателя). Чтобы позволить объекту-получателю сделать это, объект сеанса поставщика предоставляет методы в интерфейсе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)). В приложениях Visual C++ для реализации `IDBSchemaRowset` используется класс [IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md).

`IDBSchemaRowsetImpl` поддерживает следующие методы:

- [CheckRestrictions](../../data/oledb/idbschemarowsetimpl-checkrestrictions.md) проверяет допустимость ограничений для набора строк схемы.

- [CreateSchemaRowset](../../data/oledb/idbschemarowsetimpl-createschemarowset.md) реализует функцию создателя COM-объекта для объекта, указанного параметром шаблона.

- [SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md) указывает, какие ограничения поддерживаются в определенном наборе строк схемы.

- [IDBSchemaRowset::GetRowset](../../data/oledb/idbschemarowsetimpl-getrowset.md) возвращает набор строк схемы (унаследованный от интерфейса).

- [GetSchemas](../../data/oledb/idbschemarowsetimpl-getschemas.md) возвращает список наборов строк схемы, доступных для `IDBSchemaRowsetImpl::GetRowset` (унаследованных от интерфейса).

## <a name="atl-ole-db-provider-wizard-support"></a>Поддержка мастера поставщика OLE DB в ATL

::: moniker range="vs-2019"

Мастер поставщика OLE DB в ATL недоступен в Visual Studio 2019 и более поздних версиях.

::: moniker-end

::: moniker range="vs-2017"

**Мастер поставщика OLE DB в ATL** создает три класса схемы в файле заголовка сеанса:

- **C**<em>ShortName</em>**SessionTRSchemaRowset**;

- **C**<em>ShortName</em>**SessionColSchemaRowset**;

- **C**<em>ShortName</em>**SessionPTSchemaRowset**.

Эти классы отвечают на запросы объектов-получателей сведений о схеме. Обратите внимание, что спецификация OLE DB требует поддержки этих трех наборов строк схемы:

- **C**<em>ShortName</em>**SessionTRSchemaRowset** обрабатывает запросы сведений таблицы (набор строк схемы DBSCHEMA_TABLES).

- **C**<em>ShortName</em>**SessionColSchemaRowset** обрабатывает запросы сведений столбца (набор строк схемы DBSCHEMA_TABLES). Мастер предоставляет примеры реализаций для этих классов, которые возвращают сведения схемы для поставщика DOS.

- **C**<em>ShortName</em>**SessionPTSchemaRowset** обрабатывает запросы сведений схемы о типе поставщика (набор строк схемы DBSCHEMA_PROVIDER_TYPES). Реализация по умолчанию, предоставленная мастером, возвращает S_OK.

Вы можете настроить эти классы для обработки сведений схемы в зависимости от поставщика:

- В **C**<em>ShortName</em>**SessionTRSchemaRowset** необходимо заполнить поля каталога, таблицы и описания (`trData.m_szType`, `trData.m_szTable` и `trData.m_szDesc`). В созданном мастером примере используется только одна строка (таблица). Другие поставщики могут возвращать несколько таблиц.

- В **C**<em>ShortName</em>**SessionColSchemaRowset** вы передаете имя таблицы как `DBID`.

::: moniker-end

## <a name="setting-restrictions"></a>Ограничения параметров

Важным принципом в поддержке набора строк схемы является установка ограничений. Это можно сделать с помощью `SetRestrictions`. Ограничения позволяют выбирать только совпадающие строки (например, поиск всех столбцов в таблице MyTable). Ограничения являются необязательными, и если не поддерживается ни одно ограничение (по умолчанию), всегда возвращаются все данные. Пример поставщика, поддерживающего ограничения, см. в примере [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV).

## <a name="setting-up-the-schema-map"></a>Настройка карты схемы

Настройте в файле Session.h в UpdatePV карту схемы, такую ​​как эта:

```cpp
BEGIN_SCHEMA_MAP(CUpdateSession)
    SCHEMA_ENTRY(DBSCHEMA_TABLES, CUpdateSessionTRSchemaRowset)
    SCHEMA_ENTRY(DBSCHEMA_COLUMNS, CUpdateSessionColSchemaRowset)
    SCHEMA_ENTRY(DBSCHEMA_PROVIDER_TYPES, CUpdateSessionPTSchemaRowset)
END_SCHEMA_MAP()
```

Для поддержки `IDBSchemaRowset` вы должны поддерживать DBSCHEMA_TABLES, DBSCHEMA_COLUMNS и DBSCHEMA_PROVIDER_TYPES. Добавить дополнительные наборы схем можно по своему усмотрению.

Объявите класс набора строк схемы с помощью метода `Execute`, как `CUpdateSessionTRSchemaRowset` в `UpdatePV`:

```cpp
class CUpdateSessionTRSchemaRowset :
    public CSchemaRowsetImpl < CUpdateSessionTRSchemaRowset,
                              CTABLESRow, CUpdateSession >
...
// Execute looks like this; what pointers does the consumer use?
    HRESULT Execute(DBROWCOUNT* pcRowsAffected,
                    ULONG cRestrictions, const VARIANT* rgRestrictions)
```

`CUpdateSession` наследуется от `IDBSchemaRowsetImpl`, поэтому у него есть все методы обработки ограничений. Используя `CSchemaRowsetImpl`, объявите три дочерних класса (перечислены на карте схемы выше): `CUpdateSessionTRSchemaRowset`, `CUpdateSessionColSchemaRowset` и `CUpdateSessionPTSchemaRowset`. У каждого из этих дочерних классов есть метод `Execute`, который обрабатывает свой соответствующий набор ограничений (критерии поиска). Каждый метод `Execute` сравнивает значения параметров *cRestrictions* и *rgRestrictions*. Описание этих параметров см. в разделе [IDBSchemaRowsetImpl::SetRestrictions](../../data/oledb/idbschemarowsetimpl-setrestrictions.md).

Дополнительные сведения о том, какие ограничения соответствуют определенному набору строк схемы, см. в таблице GUID наборов строк схем в разделе [IDBSchemaRowset](/previous-versions/windows/desktop/ms713686(v=vs.85)) в **справочнике программиста OLE DB** в Windows SDK.

Например, если вы включили поддержку ограничения TABLE_NAME для DBSCHEMA_TABLES, следует сделать следующее:

Сначала просмотрите схему DBSCHEMA_TABLES. Вы увидите, что она поддерживает четыре ограничения (по порядку).

|Ограничение набора строк схемы|Значение ограничения|
|-------------------------------|-----------------------|
|TABLE_CATALOG|0x1 (двоичное значение: 1)|
|TABLE_SCHEMA|0x2 (двоичное значение: 10)|
|TABLE_NAME|0x4 (двоичное значение: 100)|
|TABLE_TYPE|0x8 (двоичное значение: 1000)|

Существует один бит для каждого ограничения. Так как вам нужна поддержка только TABLE_NAME, возвращается 0x4 в элементе `rgRestrictions`. Если бы вы поддерживали TABLE_CATALOG и TABLE_NAME, возвращалось бы значение 0x5 (двоичное значение: 101).

По умолчанию реализация возвращает 0 (не поддерживает никаких ограничений) для любого запроса. UpdatePV — пример поставщика, поддерживающего ограничения.

### <a name="example"></a>Пример

Этот код взят из примера [UpdatePV](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV). `UpdatePv` поддерживает три обязательных набора строк схемы: DBSCHEMA_TABLES, DBSCHEMA_COLUMNS и DBSCHEMA_PROVIDER_TYPES. В качестве примера того, как реализовать поддержку схемы в вашем поставщике, в этом разделе рассматривается реализация набора строк DBSCHEMA_TABLE.

> [!NOTE]
> Пример кода может отличаться от указанного здесь. Его следует рассматривать как более актуальную версию.

При добавлении поддержки схемы сначала нужно определить, какие ограничения вы собираетесь поддерживать. Чтобы определить, какие ограничения доступны для вашего набора строк схемы, найдите определение `IDBSchemaRowset` в спецификации OLE DB. После основного определения вы увидите таблицу, содержащую имя набора строк схемы, количество ограничений и столбцы ограничений. Выберите набор строк схемы, который необходимо поддерживать, и запишите количество ограничений и столбцов ограничений. Например, DBSCHEMA_TABLES поддерживает четыре ограничения (TABLE_CATALOG, TABLE_SCHEMA, TABLE_NAME и TABLE_TYPE):

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

Бит представляет каждый столбец ограничений. Если вам нужна поддержка ограничения (чтобы выполнять запрос с его помощью), установите для этого бита значение 1. Если вы не хотите поддерживать ограничение, установите для этого бита значение 0. В приведенной выше строке кода `UpdatePV` поддерживает ограничения TABLE_NAME и TABLE_TYPE для набора строк DBSCHEMA_TABLES. Это третье (битовая маска 100) и четвертое (битовая маска 1000) ограничения. Следовательно, битовая маска для `UpdatePv` равна 1100 (или 0x0C):

```cpp
if (InlineIsEqualGUID(rguidSchema[l], DBSCHEMA_TABLES))
    rgRestrictions[l] = 0x0C;
```

Следующая функция `Execute` аналогична функциям в обычных наборах строк. У вас есть три аргумента: *pcRowsActed*, *cRestrictions* и *rgRestrictions*. Переменная *pcRowsActed* является параметром вывода, с помощью которого поставщик может возвращать количество строк в наборе строк схемы. Параметр *cRestrictions* является входным параметром, содержащим количество ограничений, переданных объектом-получателем поставщику. Параметр *rgRestrictions* является массивом значений VARIANT, который содержат значения ограничений.

```cpp
HRESULT Execute(DBROWCOUNT* pcRowsAffected, ULONG cRestrictions,
                const VARIANT* rgRestrictions)
```

Переменная *cRestrictions* основана на общем количестве ограничений для набора строк схемы, независимо от того, поддерживает ли их поставщик. Так как UpdatePv поддерживает два ограничения (третье и четвертое), этот код ищет только значение *cRestrictions*, большее или равное третьему.

Значение для ограничения TABLE_NAME хранится в *rgRestrictions[2]* (третьим ограничением в массиве, начинающемся с нуля, является 2). Убедитесь, что ограничение не имеет значение VT_EMPTY, чтобы фактически его поддерживать. Обратите внимание, что VT_NULL не равно VT_EMPTY. VT_NULL указывает допустимое значение ограничения.

Определением `UpdatePv` имени таблицы является полное имя пути к текстовому файлу. Извлеките значение ограничения и попробуйте открыть файл, чтобы убедиться, что он действительно существует. Если файл не существует, возвращается S_OK. Это выглядит как в обратном порядке, но на самом деле код сообщает объекту-получателю об отсутствии поддерживаемых таблиц с указанным именем. Если возвращается S_OK, значит код выполнен правильно.

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

Реализация поддержки четвертого ограничения (TABLE_TYPE) аналогична реализации поддержки третьего. Убедитесь, что VT_EMPTY не является значением. В результате ограничения возвращается только тип таблицы, TABLE. Чтобы определить действительные значения для DBSCHEMA_TABLES, ознакомьтесь с **Приложением B** в **справочнике программиста OLE DB** в разделе набора строк TABLES.

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

Именно здесь вы фактически создаете запись для набора строк. Переменная `trData` соответствует `CTABLESRow`, структуре, определенной в шаблонах поставщика OLE DB. `CTABLESRow` соответствует определению набора строк TABLES в **Приложении B** спецификации OLE DB. Вам нужно добавить одну строку, так как вы можете поддерживать только одну таблицу за раз.

```cpp
// Bring over the data:
wcspy_s(trData.m_szType, OLESTR("TABLE"), 5);

wcspy_s(trData.m_szDesc, OLESTR("The Directory Table"), 19);

wcsncpy_s(trData.m_szTable, T2OLE(szFile), _TRUNCATE());
```

`UpdatePV` настраивает только три столбца: TABLE_NAME, TABLE_TYPE и DESCRIPTION. Запишите столбцы, для которых возвращаются сведения, так как они понадобятся вам при реализации `GetDBStatus`:

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

Функция `GetDBStatus` важна для правильной работы набора строк схемы. Так как данные для каждого столбца в наборе строк TABLES не возвращаются, необходимо указать, для каких столбцов вы возвращаете данные, а для каких — нет.

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

Так как функция `Execute` возвращает данные для полей TABLE_NAME, TABLE_TYPE и DESCRIPTION из набора строк TABLES, с помощью **Приложения B** спецификации OLE DB можно определить (считая сверху вниз), что они являются порядковыми числами 3, 4 и 6. Для каждого из этих столбцов возвращается DBSTATUS_S_OK. Для всех остальных столбцов возвращается DBSTATUS_S_ISNULL. Важно вернуть это состояние, так как объект-получатель может не понимать, что возвращаемое значение равно NULL или другому значению. Снова обратите внимание, что NULL не эквивалентно пустому значению.

Дополнительные сведения об интерфейсе набора строк схемы OLE DB см. в статье о [классе IDBSchemaRowsetImpl](../../data/oledb/idbschemarowsetimpl-class.md) в **справочнике программиста OLE DB**.

Дополнительные сведения о том, как объекты-получатели могут использовать методы `IDBSchemaRowset`, см. в статье [Obtaining Metadata with Schema Rowsets](../../data/oledb/obtaining-metadata-with-schema-rowsets.md) (Получение метаданных с наборами строк схемы).

C примером поставщика, который поддерживает наборы строк схемы, можно ознакомиться в [этой статье](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/ATL/OLEDB/Provider/UPDATEPV).

## <a name="see-also"></a>См. также

[Дополнительные способы использования поставщика](../../data/oledb/advanced-provider-techniques.md)
